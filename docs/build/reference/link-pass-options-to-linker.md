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
ms.openlocfilehash: 7f40841b82db9f46019ce2a96a61a1a0f622b6d5
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57813437"
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

**/Link**オプションとリンカー オプションは、ファイル名と CL オプションの後に表示する必要があります。 スペースは間で必要な **/link**と`linkeroptions`します。 詳細については、次を参照してください。 [MSVC リンカー参照](linking.md)します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)します。

1. をクリックして、**リンカー**フォルダー。

1. リンカー プロパティ ページをクリックします。

1. 1 つまたは複数のプロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- このコンパイラ オプションをプログラムで変更することはできません。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンドラインの構文](compiler-command-line-syntax.md)
