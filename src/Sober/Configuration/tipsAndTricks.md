# Tips and Tricks

## Asset Overlay

The files in `asset_overlay` located at `~/.var/app/org.vinegarhq.Sober/data/sober` will get used over the ones used by Roblox. Depending on the directory the files were placed in, this will allow for modifications to be made! The modifications will happen after an app restart, and is reversable simply by clearing out the directory.

The `asset_overlay` directory mirrors `packages/com.roblox.client/base.apk/assets` when viewed through an archive manager. **This means you have to recreate the folder sturcture as seen in the archive into `asset_overlay` in order for your modifications to work!** Example of replacing the mouse cursor:

```
~/.var/app/org.vinegarhq.Sober/data/sober/asset_overlay
└── content
    └── textures
        └── Cursors
            └── KeyboardMouse
                ├── ArrowCursor.png
                ├── ArrowFarCursor.png
                └── IBeamCursor.png
```

## Fullscreen

The toggle for fullscreen in the Roblox app has never worked on mobile builds. However, this can be replicated by pressing the `F11` key. 

> Note that Sober remembers the fullscreen state, and will automatically fullscreen again on a relaunch. You cannot close Sober within the Roblox app as well.

## FFlags

FFlags (or "Fast Flags") allows for local configuration overrides for the Roblox client. This system was originally developed to be used by Roblox engineers to dynamically update engine configurations on the fly via. OTA configuration updates rather than pushing an update every time.

Since September 2025, Fast Flags have since been locked down to a select few in [a whitelist system](https://devforum.roblox.com/t/allowlist-for-local-client-configuration-via-fast-flags/3966569).

### Geometry Fast Flags
| FFlag Name                                    | Type          | Description                                                               | Accepted Values    |
| --------------------------------------------- | ------------- | ------------------------------------------------------------------------- | ------------------ |
| `DFIntCSGLevelOfDetailSwitchingDistance`      | integer       | TBD                                                                       |                    |
| `DFIntCSGLevelOfDetailSwitchingDistanceL12`   | integer       | TBD                                                                       |                    |
| `DFIntCSGLevelOfDetailSwitchingDistanceL23`   | integer       | TBD                                                                       |                    |
| `DFIntCSGLevelOfDetailSwitchingDistanceL34`   | integer       | TBD                                                                       |                    |

### Rendering Fast Flags
| FFlag Name                                    | Type          | Description                                                               | Accepted Values    |
| --------------------------------------------- | ------------- | ------------------------------------------------------------------------- | ------------------ |
| `FFlagHandleAltEnterFullscreenManually`       | bool          | TBD                                                                       |                    |
| `DFFlagTextureQualityOverrideEnabled`         | bool          | Enables texture quality to be overrided by `DFIntTextureQualityOverride`  |                    |
| `DFIntTextureQualityOverride`                 | integer       | Sets texture quality level. (`DFFlagTextureQualityOverrideEnabled` must be set to true first) |           |
| `FIntDebugForceMSAASamples`                   | integer       | Force MSAA anti-aliasing sample rate                                      |                    |
| `DFFlagDisableDPIScale`                       | bool          | TBD                                                                       |                    |
| `FFlagDebugGraphicsPreferD3D11`               | bool          | Prefers DirectX 11 for rendering (is not relevant for Sober)              |                    |
| `FFlagDebugSkyGray`                           | bool          | Overrides the skybox color to gray, removes atmospheric stars             |                    |
| `DFFlagDebugPauseVoxelizer`                   | bool          | TBD                                                                       |                    |
| `DFIntDebugFRMQualityLevelOverride`           | bool          | TBD                                                                       |                    |
| `FIntFRMMaxGrassDistance`                     | integer       | Sets the maximum distance for grass rendering                             |                    |
| `FIntFRMMinGrassDistance`                     | integer       | Sets the minimum distance for grass rendering                             |                    |
| `FFlagDebugGraphicsPreferVulkan`              | bool          | Prefers Vulkan for rendering                                              |                    |
| `FFlagDebugGraphicsPreferOpenGL`              | bool          | Prefers OpenGL for rendering                                              |                    |

### User interface Fast Flags
| FFlag Name                                    | Type          | Description                                                               | Accepted Values    |
| --------------------------------------------- | ------------- | ------------------------------------------------------------------------- | ------------------ |
| `FIntGrassMovementReducedMotionFactor`        | integer       | Reduces grass movement by `x` studs                                       |                    |