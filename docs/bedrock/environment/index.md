
### OS OPTIONS

<table style="width:100%">
  <thead>
    <tr>
      <th>NAME</th>
      <th>DESCRIPTION</th>
      <th>DEFAULT</th>
      <th>REQUIRED</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>EULA</code></td>
      <td>You <strong>MUST</strong> set this to <code>TRUE</code> to accept the <a href="https://minecraft.net/terms">Minecraft End User License Agreement</a>.</td>
      <td><code>&nbsp;</code></td>
      <td>✅</td>
    </tr>
    <tr>
      <td><code>VERSION</code></td>
      <td>Can be set to a specific server version or the following special values can be used:
        <ul>
          <li><code>LATEST</code>: The latest (non-preview) version and can be used to auto-upgrade on container start.</li>
          <li><code>PREVIEW</code>: The latest preview version and will auto-upgrade.</li>
          <li><code>PREVIOUS</code>: Uses the previously maintained major version. Useful when the mobile app is gradually being upgraded across devices</li>
          <li><code>1.11</code>: The latest version of 1.11</li>
          <li><code>1.12</code>: The latest version of 1.12</li>
          <li><code>1.13</code>: The latest version of 1.13</li>
          <li><code>1.14</code>: The latest version of 1.14</li>
          <li><code>1.16</code>: The latest version of 1.16</li>
          <li>Any specific server version can be provided. If it is a preview version, also set <code>PREVIEW</code> to `true`</li>
        </ul>
      </td>
      <td><code>LATEST</code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>PREVIEW</code></td>
      <td>Set to <code>true</code> if the version you are specifying is a PREVIEW version</td>
      <td><code>false</code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>UID</code></td>
      <td>The linux user id to run as</td>
      <td>derived from <code>/data</code> owner</td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>GID</code></td>
      <td>The linux group id to run as</td>
      <td>derived from <code>/data</code> owner</td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>PACKAGE_BACKUP_KEEP </code></td>
      <td>The number of package backups to keep</td>
      <td><code>2</code></td>
      <td>⬜️</td>
    </tr>
  </tbody>
</table>

### SERVER PROPERTIES

<table style="width:100%">
  <thead>
    <tr>
      <th>NAME</th>
      <th>DESCRIPTION</th>
      <th>DEFAULT</th>
      <th>REQUIRED</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>SERVER_NAME</code></td>
      <td></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>SERVER_PORT</code></td>
      <td></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>SERVER_PORT_V6</code></td>
      <td></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>GAMEMODE</code></td>
      <td></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>DIFFICULTY</code></td>
      <td></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>LEVEL_TYPE</code></td>
      <td></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>ALLOW_CHEATS</code></td>
      <td></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>MAX_PLAYERS</code></td>
      <td></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>ONLINE_MODE</code></td>
      <td></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>WHITE_LIST</code></td>
      <td></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>VIEW_DISTANCE</code></td>
      <td></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>TICK_DISTANCE</code></td>
      <td></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>PLAYER_IDLE_TIMEOUT</code></td>
      <td></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>MAX_THREADS</code></td>
      <td></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>LEVEL_NAME</code></td>
      <td></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>LEVEL_SEED</code></td>
      <td></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>DEFAULT_PLAYER_PERMISSION_LEVEL</code></td>
      <td></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>TEXTUREPACK_REQUIRED</code></td>
      <td></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>SERVER_AUTHORITATIVE_MOVEMENT</code></td>
      <td></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>PLAYER_MOVEMENT_SCORE_THRESHOLD</code></td>
      <td></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>PLAYER_MOVEMENT_DISTANCE_THRESHOLD</code></td>
      <td></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>PLAYER_MOVEMENT_DURATION_THRESHOLD_IN_MS</code></td>
      <td></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>CORRECT_PLAYER_MOVEMENT</code></td>
      <td></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
  </tbody>
</table>
