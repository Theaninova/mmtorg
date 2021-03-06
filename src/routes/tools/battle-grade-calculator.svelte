<script>
  import "../../lib/style/table.scss"
  import "../../lib/style/rank-themes.scss"

  import CalculatorFooter from "../../lib/components/CalculatorFooter.svelte"
  import MedalHeader from "../../lib/components/MedalHeader.svelte"
  import RankTitle from "../../lib/components/RankTitle.svelte"

  import {calculateRank} from "../../lib/tools/aura-calculator.ts"
  import {medalValues} from "../../lib/tools/data/medal-values.ts"
  import Output from "../../lib/components/table/Output.svelte"
  import Input from "../../lib/components/table/Input.svelte"
  import Lightbar from "../../lib/components/Lightbar.svelte"
  import HeaderPadding from "../../lib/components/HeaderPadding.svelte"

  let input = Object.fromEntries(Object.entries(medalValues).map(([key]) => [key, 0]))

  $: result = calculateRank(input)
</script>

<svelte:head>
  <title>Battle Grade Calculator</title>
  <meta name="description" content="Battle Grade Calculator for Wangan Midnight Maximum Tune" />
</svelte:head>

<HeaderPadding />

<form>
  <table>
    <thead>
      <tr>
        <MedalHeader />
      </tr>
    </thead>
    <tr>
      {#each Object.entries(medalValues) as [medalName]}
        <Input
          on:change={event => (input = {...input, [medalName]: Number(event.target.value)})}
          id={medalName}
          type="number"
          placeholder="0"
          name={medalName}
        />
      {/each}
    </tr>
  </table>
</form>

<Lightbar />

<section class="center">
  <RankTitle class="rank-theme-gold">{result.rankName}</RankTitle>
  <p><a href="/tools/battle-grade-info">See how we calculate your rank</a></p>

  <table>
    <caption>Total</caption>
    <thead>
      <tr>
        <th style="height: 21px">Points</th>
        <th style="height: 21px">Medals</th>
      </tr>
    </thead>
    <tr>
      <Output>{result.totalScore}</Output>
      <Output>{result.totalMedals}</Output>
    </tr>
  </table>
  {#if result.nextRank}
    <table>
      <caption>Points until next rank</caption>
      <thead>
        <tr>
          <th>Total</th>
          <MedalHeader />
        </tr>
      </thead>
      <tr>
        <Output>{result.nextRank.nextRankDifference}</Output>
        {#each result.nextRank.differences as [name, value]}
          <Output>{value}</Output>
        {/each}
      </tr>
    </table>
  {/if}
</section>

<CalculatorFooter />

<style>
  caption {
    min-height: 26px;
  }
</style>
