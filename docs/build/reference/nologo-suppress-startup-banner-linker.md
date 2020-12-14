---
description: 詳細については、「/NOLOGO (著作権情報の非表示) (リンカー)」を参照してください。
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
ms.openlocfilehash: 48edea691e254f0754d29ab5ea4d8055221c4b69
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196556"
---
# <a name="nologo-suppress-startup-banner-linker"></a>/NOLOGO (著作権情報の非表示) (リンカー)

```
/NOLOGO
```

## <a name="remarks"></a>解説

/NOLOGO オプションを指定すると、著作権メッセージとバージョン番号が表示されなくなります。

このオプションでは、コマンドファイルのエコーも抑制します。 詳細については、「 [LINK コマンドファイル](linking.md)」を参照してください。

既定では、この情報はリンカーによって出力ウィンドウに送信されます。 コマンドラインでは、標準出力に送信され、ファイルにリダイレクトできます。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. このオプションは、コマンドラインからのみ使用してください。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. このリンカーオプションは、プログラムによって変更することはできません。

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
