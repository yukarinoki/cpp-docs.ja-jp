---
title: --link (リンカーに渡すオプション) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /link
dev_langs:
- C++
helpviewer_keywords:
- /link compiler option [C++]
- pass options to linker
- link compiler option [C++]
- linker [C++], passing options to
- -link compiler option [C++]
- cl.exe compiler [C++], passing options to linker
ms.assetid: 16902a94-c094-4328-841f-3ac94ca04848
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 663407e4948ebc4e3c0a1676c44e8d2b4bd53fcc
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45704120"
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

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. をクリックして、**リンカー**フォルダー。

1. リンカー プロパティ ページをクリックします。

1. 1 つまたは複数のプロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- このコンパイラ オプションをプログラムで変更することはできません。

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)