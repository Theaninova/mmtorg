<script>
  import "../../lib/style/table.scss"
</script>

<table>
  <caption>File Formats</caption>
  <thead>
    <tr>
      <th>Extension</th>
      <th>Relation</th>
      <th>Purpose</th>
      <th>Solved</th>
      <th>Import</th>
      <th>Export</th>
      <th>Format</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>.lua</td>
      <td>Scripting</td>
      <td>Lua script</td>
      <td partial />
      <td no />
      <td yes />
      <td text />
    </tr>
    <tr>
      <td>.LMD</td>
      <td>Menus</td>
      <td unknown />
      <td no />
      <td no />
      <td no />
      <td binary />
    </tr>
    <tr>
      <td>.xlsm</td>
      <td>Translation</td>
      <td>Excel spreadsheet</td>
      <td yes />
      <td yes />
      <td yes />
      <td text />
    </tr>
    <tr>
      <td>.xmlt</td>
      <td>Config</td>
      <td unknown />
      <td no />
      <td no />
      <td no />
      <td text />
    </tr>
    <tr>
      <td>.bin (Config)</td>
      <td>Config</td>
      <td unknown />
      <td no />
      <td no />
      <td no />
      <td binary />
    </tr>
    <tr>
      <td><a href="/tools/bin-soundbank-editor">.bin (Index Map)</a></td>
      <td>Config</td>
      <td>Record<br /><code>int ⇒ string</code></td>
      <td yes />
      <td yes />
      <td wip />
      <td binary />
    </tr>
    <tr>
      <td><a href="/tools/bin-soundbank-editor">.bin (String Map)</a></td>
      <td>Config</td>
      <td>Record<br /><code>string ⇒ string</code></td>
      <td yes />
      <td yes />
      <td wip />
      <td binary />
    </tr>
    <tr>
      <td><a href="https://mpc-hc.org/">.wmv</a></td>
      <td>Video</td>
      <td>Windows Media Video</td>
      <td yes />
      <td yes />
      <td yes />
      <td binary />
    </tr>
    <tr>
      <td><a href="/tools/nub-converter">.nub</a></td>
      <td>Sound</td>
      <td>Wav based sound bank</td>
      <td partial />
      <td partial />
      <td no />
      <td binary />
    </tr>
    <tr>
      <td>.tbl</td>
      <td>Sound</td>
      <td unknown />
      <td no />
      <td no />
      <td no />
      <td text />
    </tr>
    <tr>
      <td>.nuf</td>
      <td>Font</td>
      <td>Font Descriptor</td>
      <td no />
      <td no />
      <td no />
      <td binary />
    </tr>
    <tr>
      <td
        ><a
          href="https://github.com/jam1garner/Smash-Forge/blob/master/Smash%20Forge/Filetypes/Textures/NUT.cs"
          >.nut</a
        ></td
      >
      <td>Texture</td>
      <td>Texture files</td>
      <td yes />
      <td wip />
      <td no />
      <td binary />
    </tr>
    <tr>
      <td><a href="https://www.gnu.org/software/gzip/">.nut (gzipped)</a></td>
      <td>Texture</td>
      <td>Gzip compressed .nut texture</td>
      <td yes />
      <td yes />
      <td yes />
      <td binary />
    </tr>
    <tr>
      <td><a href="https://www.gnu.org/software/gzip/">.tex</a></td>
      <td>Texture</td>
      <td>Gzip compressed .nut texture</td>
      <td yes />
      <td yes />
      <td yes />
      <td binary />
    </tr>
    <tr>
      <td>.nud</td>
      <td>Model </td>
      <td>Model file</td>
      <td yes />
      <td wip />
      <td wip />
      <td binary />
    </tr>
    <tr>
      <td><a href="https://www.gnu.org/software/gzip/">.mdl</a></td>
      <td>Model</td>
      <td>Gzip compressed XMD.001 .nud archive</td>
      <td yes />
      <td yes />
      <td yes />
      <td binary />
    </tr>
    <tr>
      <td><a href="/file-formats/path-bin">.bin (path)</a></td>
      <td>Model</td>
      <td>3D Paths for tracks</td>
      <td yes />
      <td yes />
      <td wip />
      <td binary />
    </tr>
    <tr>
      <td><a href="https://www.gnu.org/software/gzip/">.gz</a></td>
      <td>Archive</td>
      <td>Gzip Archive</td>
      <td yes />
      <td yes />
      <td yes />
      <td binary />
    </tr>
    <tr>
      <td>.bin (XMD.001)</td>
      <td>Archive</td>
      <td>Archive of multiple files</td>
      <td yes />
      <td wip />
      <td wip />
      <td binary />
    </tr>
    <tr>
      <td>.nsh</td>
      <td>Shading</td>
      <td unknown />
      <td no />
      <td no />
      <td no />
      <td binary />
    </tr>
    <tr>
      <td>.ACT</td>
      <td>Shading</td>
      <td unknown />
      <td no />
      <td no />
      <td no />
      <td binary />
    </tr>
    <tr>
      <td>.MED</td>
      <td>Motion</td>
      <td unknown />
      <td no />
      <td no />
      <td no />
      <td binary />
    </tr>
    <tr>
      <td>.bin (Ghost)</td>
      <td>Savestate</td>
      <td unknown />
      <td no />
      <td no />
      <td no />
      <td binary />
    </tr>
    <tr>
      <td>.conf (Network)</td>
      <td>Network</td>
      <td>Network configuration</td>
      <td partial />
      <td no />
      <td no />
      <td text />
    </tr>
    <tr>
      <td>.txt (Enma)</td>
      <td>Enma</td>
      <td unknown />
      <td no />
      <td no />
      <td no />
      <td text />
    </tr>

    <tr>
      <td><a href="https://www.digicert.com/kb/ssl-support/pem-ssl-creation.htm">.pem</a></td>
      <td>Certificate</td>
      <td>Network Certificate</td>
      <td yes />
      <td yes />
      <td yes />
      <td text />
    </tr>

    <tr>
      <td>.EES</td>
      <td unknown />
      <td unknown />
      <td no />
      <td no />
      <td no />
      <td binary />
    </tr>
  </tbody>
</table>

<style>
  table {
    border-collapse: separate;
    border-spacing: 8px;
  }

  td:not(:first-child) {
    text-align: center;
  }

  td[unknown]::after {
    content: "?";
    color: red;
  }

  td[yes]::after {
    content: "✓";
    color: green;
  }

  td[no]::after {
    content: "✗";
    color: red;
  }

  td[partial]::after {
    content: "(✓)";
    color: orange;
  }

  td[wip]::after {
    content: "WIP";
    color: orange;
  }

  td[binary]::after {
    content: "bin";
  }

  td[text]::after {
    content: "text";
    color: green;
  }
</style>
