# Scroll sync in a long document (#267)

Edit this file with the preview shown (press `:`), then scroll the source
from top to bottom with the wheel. The preview must follow all the way to
the end. In 3.8.1 it stopped at section 8, whose YAML block opens with an
indented line, and only moved again once the source was scrolled back up.

## Contents

1. [Overview](#1-overview)
2. [Prerequisites](#2-prerequisites)
3. [Creating the vault](#3-creating-the-vault)
4. [Certificates](#4-certificates)
5. [Signing locally](#5-signing-locally)
6. [Pipeline secrets](#6-pipeline-secrets)
7. [Build agents](#7-build-agents)
8. [Release workflow](#8-release-workflow)
9. [Verifying signatures](#9-verifying-signatures)
10. [Rotating keys](#10-rotating-keys)
11. [Troubleshooting](#11-troubleshooting)
12. [Logging](#12-logging)
13. [Access policies](#13-access-policies)
14. [Backups](#14-backups)
15. [Monitoring](#15-monitoring)
16. [Costs](#16-costs)
17. [Migration](#17-migration)
18. [Testing](#18-testing)
19. [Rollout](#19-rollout)
20. [Appendix](#20-appendix)

## 1. Overview

This section covers **overview** for the signing setup. It is long enough to
wrap in a narrow source pane, with *emphasis*, `inline code` and a
[link to the contents](#contents) so the preview has varied text to lay out.

> ⚠️ **Note:** step 1 assumes the previous steps are done. Check the
> vault name before running anything that signs.

| Setting | Value | Notes |
| --- | --- | --- |
| Step | 1 | `Overview` |
| Owner | Release team | reviewed weekly |

![Screen 1](../assets/screen-2.png)

```powershell
Get-AuthenticodeSignature .\tinta.exe | Format-List
```

- First point about this step, with a little more text after it.
- Second point, which links back to [the top](#scroll-sync-in-a-long-document-267).
  - A nested point.

### 1.1 Details

A closing paragraph for the section. Lorem ipsum dolor sit amet, consectetur
adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

## 2. Prerequisites

This section covers **prerequisites** for the signing setup. It is long enough to
wrap in a narrow source pane, with *emphasis*, `inline code` and a
[link to the contents](#contents) so the preview has varied text to lay out.

> ⚠️ **Note:** step 2 assumes the previous steps are done. Check the
> vault name before running anything that signs.

```json
{
  "vault": "release-signing",
  "certificate": "code-signing-2026",
  "rotateDays": 365
}
```

- First point about this step, with a little more text after it.
- Second point, which links back to [the top](#scroll-sync-in-a-long-document-267).
  - A nested point.

### 2.1 Details

A closing paragraph for the section. Lorem ipsum dolor sit amet, consectetur
adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

## 3. Creating the vault

This section covers **creating the vault** for the signing setup. It is long enough to
wrap in a narrow source pane, with *emphasis*, `inline code` and a
[link to the contents](#contents) so the preview has varied text to lay out.

> ⚠️ **Note:** step 3 assumes the previous steps are done. Check the
> vault name before running anything that signs.

| Setting | Value | Notes |
| --- | --- | --- |
| Step | 3 | `Creating the vault` |
| Owner | Release team | reviewed weekly |

```powershell
Get-AuthenticodeSignature .\tinta.exe | Format-List
```

- First point about this step, with a little more text after it.
- Second point, which links back to [the top](#scroll-sync-in-a-long-document-267).
  - A nested point.

### 3.1 Details

A closing paragraph for the section. Lorem ipsum dolor sit amet, consectetur
adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

## 4. Certificates

This section covers **certificates** for the signing setup. It is long enough to
wrap in a narrow source pane, with *emphasis*, `inline code` and a
[link to the contents](#contents) so the preview has varied text to lay out.

> ⚠️ **Note:** step 4 assumes the previous steps are done. Check the
> vault name before running anything that signs.

![Screen 4](../assets/screen-1.png)

```csharp
public sealed class SigningClient
{
    private readonly HttpClient _http;

    public SigningClient(HttpClient http) => _http = http;

    public async Task<byte[]> SignAsync(byte[] digest)
    {
        var response = await _http.PostAsync("sign", new ByteArrayContent(digest));
        response.EnsureSuccessStatusCode();
        return await response.Content.ReadAsByteArrayAsync();
    }
}
```

- First point about this step, with a little more text after it.
- Second point, which links back to [the top](#scroll-sync-in-a-long-document-267).
  - A nested point.

### 4.1 Details

A closing paragraph for the section. Lorem ipsum dolor sit amet, consectetur
adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

## 5. Signing locally

This section covers **signing locally** for the signing setup. It is long enough to
wrap in a narrow source pane, with *emphasis*, `inline code` and a
[link to the contents](#contents) so the preview has varied text to lay out.

> ⚠️ **Note:** step 5 assumes the previous steps are done. Check the
> vault name before running anything that signs.

| Setting | Value | Notes |
| --- | --- | --- |
| Step | 5 | `Signing locally` |
| Owner | Release team | reviewed weekly |

```powershell
Get-AuthenticodeSignature .\tinta.exe | Format-List
```

- First point about this step, with a little more text after it.
- Second point, which links back to [the top](#scroll-sync-in-a-long-document-267).
  - A nested point.

### 5.1 Details

A closing paragraph for the section. Lorem ipsum dolor sit amet, consectetur
adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

## 6. Pipeline secrets

This section covers **pipeline secrets** for the signing setup. It is long enough to
wrap in a narrow source pane, with *emphasis*, `inline code` and a
[link to the contents](#contents) so the preview has varied text to lay out.

> ⚠️ **Note:** step 6 assumes the previous steps are done. Check the
> vault name before running anything that signs.

```json
{
  "vault": "release-signing",
  "certificate": "code-signing-2026",
  "rotateDays": 365
}
```

- First point about this step, with a little more text after it.
- Second point, which links back to [the top](#scroll-sync-in-a-long-document-267).
  - A nested point.

### 6.1 Details

A closing paragraph for the section. Lorem ipsum dolor sit amet, consectetur
adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

## 7. Build agents

This section covers **build agents** for the signing setup. It is long enough to
wrap in a narrow source pane, with *emphasis*, `inline code` and a
[link to the contents](#contents) so the preview has varied text to lay out.

> ⚠️ **Note:** step 7 assumes the previous steps are done. Check the
> vault name before running anything that signs.

| Setting | Value | Notes |
| --- | --- | --- |
| Step | 7 | `Build agents` |
| Owner | Release team | reviewed weekly |

![Screen 7](../assets/screen-4.png)

```powershell
Get-AuthenticodeSignature .\tinta.exe | Format-List
```

- First point about this step, with a little more text after it.
- Second point, which links back to [the top](#scroll-sync-in-a-long-document-267).
  - A nested point.

### 7.1 Details

A closing paragraph for the section. Lorem ipsum dolor sit amet, consectetur
adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

## 8. Release workflow

This section covers **release workflow** for the signing setup. It is long enough to
wrap in a narrow source pane, with *emphasis*, `inline code` and a
[link to the contents](#contents) so the preview has varied text to lay out.

> ⚠️ **Note:** step 8 assumes the previous steps are done. Check the
> vault name before running anything that signs.

The workflow step, copied from the pipeline with its indentation:

```yaml
      - name: Sign the release build
        run: |
          signtool sign /fd sha256 /tr http://timestamp.example /td sha256 tinta.exe
          signtool verify /pa tinta.exe
      - name: Upload
        uses: actions/upload-artifact@v4
```

- First point about this step, with a little more text after it.
- Second point, which links back to [the top](#scroll-sync-in-a-long-document-267).
  - A nested point.

### 8.1 Details

A closing paragraph for the section. Lorem ipsum dolor sit amet, consectetur
adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

## 9. Verifying signatures

This section covers **verifying signatures** for the signing setup. It is long enough to
wrap in a narrow source pane, with *emphasis*, `inline code` and a
[link to the contents](#contents) so the preview has varied text to lay out.

> ⚠️ **Note:** step 9 assumes the previous steps are done. Check the
> vault name before running anything that signs.

| Setting | Value | Notes |
| --- | --- | --- |
| Step | 9 | `Verifying signatures` |
| Owner | Release team | reviewed weekly |

```powershell
Get-AuthenticodeSignature .\tinta.exe | Format-List
```

- First point about this step, with a little more text after it.
- Second point, which links back to [the top](#scroll-sync-in-a-long-document-267).
  - A nested point.

### 9.1 Details

A closing paragraph for the section. Lorem ipsum dolor sit amet, consectetur
adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

## 10. Rotating keys

This section covers **rotating keys** for the signing setup. It is long enough to
wrap in a narrow source pane, with *emphasis*, `inline code` and a
[link to the contents](#contents) so the preview has varied text to lay out.

> ⚠️ **Note:** step 10 assumes the previous steps are done. Check the
> vault name before running anything that signs.

![Screen 10](../assets/screen-3.png)

```json
{
  "vault": "release-signing",
  "certificate": "code-signing-2026",
  "rotateDays": 365
}
```

- First point about this step, with a little more text after it.
- Second point, which links back to [the top](#scroll-sync-in-a-long-document-267).
  - A nested point.

### 10.1 Details

A closing paragraph for the section. Lorem ipsum dolor sit amet, consectetur
adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

## 11. Troubleshooting

This section covers **troubleshooting** for the signing setup. It is long enough to
wrap in a narrow source pane, with *emphasis*, `inline code` and a
[link to the contents](#contents) so the preview has varied text to lay out.

> ⚠️ **Note:** step 11 assumes the previous steps are done. Check the
> vault name before running anything that signs.

| Setting | Value | Notes |
| --- | --- | --- |
| Step | 11 | `Troubleshooting` |
| Owner | Release team | reviewed weekly |

```powershell
Get-AuthenticodeSignature .\tinta.exe | Format-List
```

- First point about this step, with a little more text after it.
- Second point, which links back to [the top](#scroll-sync-in-a-long-document-267).
  - A nested point.

### 11.1 Details

A closing paragraph for the section. Lorem ipsum dolor sit amet, consectetur
adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

## 12. Logging

This section covers **logging** for the signing setup. It is long enough to
wrap in a narrow source pane, with *emphasis*, `inline code` and a
[link to the contents](#contents) so the preview has varied text to lay out.

> ⚠️ **Note:** step 12 assumes the previous steps are done. Check the
> vault name before running anything that signs.

```csharp
public sealed class SigningClient
{
    private readonly HttpClient _http;

    public SigningClient(HttpClient http) => _http = http;

    public async Task<byte[]> SignAsync(byte[] digest)
    {
        var response = await _http.PostAsync("sign", new ByteArrayContent(digest));
        response.EnsureSuccessStatusCode();
        return await response.Content.ReadAsByteArrayAsync();
    }
}
```

- First point about this step, with a little more text after it.
- Second point, which links back to [the top](#scroll-sync-in-a-long-document-267).
  - A nested point.

### 12.1 Details

A closing paragraph for the section. Lorem ipsum dolor sit amet, consectetur
adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

## 13. Access policies

This section covers **access policies** for the signing setup. It is long enough to
wrap in a narrow source pane, with *emphasis*, `inline code` and a
[link to the contents](#contents) so the preview has varied text to lay out.

> ⚠️ **Note:** step 13 assumes the previous steps are done. Check the
> vault name before running anything that signs.

| Setting | Value | Notes |
| --- | --- | --- |
| Step | 13 | `Access policies` |
| Owner | Release team | reviewed weekly |

![Screen 13](../assets/screen-2.png)

```powershell
Get-AuthenticodeSignature .\tinta.exe | Format-List
```

- First point about this step, with a little more text after it.
- Second point, which links back to [the top](#scroll-sync-in-a-long-document-267).
  - A nested point.

### 13.1 Details

A closing paragraph for the section. Lorem ipsum dolor sit amet, consectetur
adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

## 14. Backups

This section covers **backups** for the signing setup. It is long enough to
wrap in a narrow source pane, with *emphasis*, `inline code` and a
[link to the contents](#contents) so the preview has varied text to lay out.

> ⚠️ **Note:** step 14 assumes the previous steps are done. Check the
> vault name before running anything that signs.

```json
{
  "vault": "release-signing",
  "certificate": "code-signing-2026",
  "rotateDays": 365
}
```

- First point about this step, with a little more text after it.
- Second point, which links back to [the top](#scroll-sync-in-a-long-document-267).
  - A nested point.

### 14.1 Details

A closing paragraph for the section. Lorem ipsum dolor sit amet, consectetur
adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

## 15. Monitoring

This section covers **monitoring** for the signing setup. It is long enough to
wrap in a narrow source pane, with *emphasis*, `inline code` and a
[link to the contents](#contents) so the preview has varied text to lay out.

> ⚠️ **Note:** step 15 assumes the previous steps are done. Check the
> vault name before running anything that signs.

| Setting | Value | Notes |
| --- | --- | --- |
| Step | 15 | `Monitoring` |
| Owner | Release team | reviewed weekly |

```powershell
Get-AuthenticodeSignature .\tinta.exe | Format-List
```

- First point about this step, with a little more text after it.
- Second point, which links back to [the top](#scroll-sync-in-a-long-document-267).
  - A nested point.

### 15.1 Details

A closing paragraph for the section. Lorem ipsum dolor sit amet, consectetur
adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

## 16. Costs

This section covers **costs** for the signing setup. It is long enough to
wrap in a narrow source pane, with *emphasis*, `inline code` and a
[link to the contents](#contents) so the preview has varied text to lay out.

> ⚠️ **Note:** step 16 assumes the previous steps are done. Check the
> vault name before running anything that signs.

![Screen 16](../assets/screen-1.png)

```csharp
public sealed class SigningClient
{
    private readonly HttpClient _http;

    public SigningClient(HttpClient http) => _http = http;

    public async Task<byte[]> SignAsync(byte[] digest)
    {
        var response = await _http.PostAsync("sign", new ByteArrayContent(digest));
        response.EnsureSuccessStatusCode();
        return await response.Content.ReadAsByteArrayAsync();
    }
}
```

- First point about this step, with a little more text after it.
- Second point, which links back to [the top](#scroll-sync-in-a-long-document-267).
  - A nested point.

### 16.1 Details

A closing paragraph for the section. Lorem ipsum dolor sit amet, consectetur
adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

## 17. Migration

This section covers **migration** for the signing setup. It is long enough to
wrap in a narrow source pane, with *emphasis*, `inline code` and a
[link to the contents](#contents) so the preview has varied text to lay out.

> ⚠️ **Note:** step 17 assumes the previous steps are done. Check the
> vault name before running anything that signs.

| Setting | Value | Notes |
| --- | --- | --- |
| Step | 17 | `Migration` |
| Owner | Release team | reviewed weekly |

The workflow step, copied from the pipeline with its indentation:

```yaml
      - name: Sign the release build
        run: |
          signtool sign /fd sha256 /tr http://timestamp.example /td sha256 tinta.exe
          signtool verify /pa tinta.exe
      - name: Upload
        uses: actions/upload-artifact@v4
```

- First point about this step, with a little more text after it.
- Second point, which links back to [the top](#scroll-sync-in-a-long-document-267).
  - A nested point.

### 17.1 Details

A closing paragraph for the section. Lorem ipsum dolor sit amet, consectetur
adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

## 18. Testing

This section covers **testing** for the signing setup. It is long enough to
wrap in a narrow source pane, with *emphasis*, `inline code` and a
[link to the contents](#contents) so the preview has varied text to lay out.

> ⚠️ **Note:** step 18 assumes the previous steps are done. Check the
> vault name before running anything that signs.

```json
{
  "vault": "release-signing",
  "certificate": "code-signing-2026",
  "rotateDays": 365
}
```

- First point about this step, with a little more text after it.
- Second point, which links back to [the top](#scroll-sync-in-a-long-document-267).
  - A nested point.

### 18.1 Details

A closing paragraph for the section. Lorem ipsum dolor sit amet, consectetur
adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

## 19. Rollout

This section covers **rollout** for the signing setup. It is long enough to
wrap in a narrow source pane, with *emphasis*, `inline code` and a
[link to the contents](#contents) so the preview has varied text to lay out.

> ⚠️ **Note:** step 19 assumes the previous steps are done. Check the
> vault name before running anything that signs.

| Setting | Value | Notes |
| --- | --- | --- |
| Step | 19 | `Rollout` |
| Owner | Release team | reviewed weekly |

![Screen 19](../assets/screen-4.png)

```powershell
Get-AuthenticodeSignature .\tinta.exe | Format-List
```

- First point about this step, with a little more text after it.
- Second point, which links back to [the top](#scroll-sync-in-a-long-document-267).
  - A nested point.

### 19.1 Details

A closing paragraph for the section. Lorem ipsum dolor sit amet, consectetur
adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

## 20. Appendix

This section covers **appendix** for the signing setup. It is long enough to
wrap in a narrow source pane, with *emphasis*, `inline code` and a
[link to the contents](#contents) so the preview has varied text to lay out.

> ⚠️ **Note:** step 20 assumes the previous steps are done. Check the
> vault name before running anything that signs.

```csharp
public sealed class SigningClient
{
    private readonly HttpClient _http;

    public SigningClient(HttpClient http) => _http = http;

    public async Task<byte[]> SignAsync(byte[] digest)
    {
        var response = await _http.PostAsync("sign", new ByteArrayContent(digest));
        response.EnsureSuccessStatusCode();
        return await response.Content.ReadAsByteArrayAsync();
    }
}
```

- First point about this step, with a little more text after it.
- Second point, which links back to [the top](#scroll-sync-in-a-long-document-267).
  - A nested point.

### 20.1 Details

A closing paragraph for the section. Lorem ipsum dolor sit amet, consectetur
adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

## Last section

The preview must reach this line when the source does.
