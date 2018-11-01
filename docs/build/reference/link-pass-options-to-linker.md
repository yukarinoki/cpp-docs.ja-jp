---
title: /link (リンカーにオプションを渡す)
ms.date: 11/04/2016
f1_keywords:
- /link
helpviewer_keywords:
- /link compiler option [C++]
- pass options to linker
- link compiler option [C++]
- linker [C++], passing options to
- -link compiler option [C++]
- cl.exe compiler [C++], passing options to linker
ms.assetid: 16902a94-c094-4328-841f-3ac94ca04848
ms.openlocfilehash: dfa39988782a0c5bd121b6e18402d3f6b67a13e9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50574929"
---
# <a name="link-pass-options-to-linker"></a>/link (リンカーにオプションを渡す)

1 つまたは複数のリンカー オプションをリンカーに渡します。

## <a name="syntax"></a>構文

```
/link linkeroptions
```

## <a name="arguments"></a>引数

*linkeroptions*<br/>
リンカー オプションまたはリンカーに渡されるオプション。

## <a name="remarks"></a>Remarks

**/Link**オプションとリンカー オプションは、ファイル名と CL オプションの後に表示する必要があります。 スペースは間で必要な **/link**と`linkeroptions`します。 詳細については、次を参照してください。[リンカー オプションの設定](../../build/reference/setting-linker-options.md)します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. をクリックして、**リンカー**フォルダー。

1. リンカー プロパティ ページをクリックします。

1. 1 つまたは複数のプロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- このコンパイラ オプションをプログラムで変更することはできません。

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)