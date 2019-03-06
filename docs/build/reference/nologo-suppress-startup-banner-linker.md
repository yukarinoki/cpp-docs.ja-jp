---
title: /NOLOGO (著作権情報の非表示) (リンカー)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.SuppressStartupBanner
- /nologo
helpviewer_keywords:
- suppress startup banner linker option
- -NOLOGO linker option
- /NOLOGO linker option
- copyright message
- version numbers, preventing linker display
- banners, suppressing startup
- NOLOGO linker option
ms.assetid: 3b20dddd-eca6-4545-a331-9f70bf720197
ms.openlocfilehash: 1b966c1f7af556a85aadcafaa8ed43da5b3f75df
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57422157"
---
# <a name="nologo-suppress-startup-banner-linker"></a>/NOLOGO (著作権情報の非表示) (リンカー)

```
/NOLOGO
```

## <a name="remarks"></a>Remarks

/NOLOGO オプションでは、著作権のメッセージとバージョン番号が表示されなくなります。

このオプションはまた、コマンド ファイルのエコーを抑制します。 詳細については、次を参照してください。 [LINK コマンド ファイル](../../build/reference/link-command-files.md)します。

既定では、この情報は、出力ウィンドウに、リンカーによって送信されます。 コマンドラインでは、標準出力に送信され、ファイルにリダイレクトできます。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. このオプションは、コマンドラインからのみ使用する必要があります。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. このリンカー オプションをプログラムで変更することはできません。

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)
