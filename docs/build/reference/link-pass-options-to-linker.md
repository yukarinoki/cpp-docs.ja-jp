---
title: /link (リンカーにオプションを渡す)
ms.date: 03/25/2019
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
ms.openlocfilehash: ef81a6617df811660506c08434f3b65e29155794
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62290684"
---
# <a name="link-pass-options-to-linker"></a>/link (リンカーにオプションを渡す)

1 つまたは複数のリンカー オプションをリンカーに渡します。

## <a name="syntax"></a>構文

> **/link** *linker-options*

## <a name="arguments"></a>引数

*リンカー オプション*<br/>
リンカー オプションまたはリンカーに渡されるオプション。

## <a name="remarks"></a>Remarks

**/Link**オプションとリンカー オプションは、ファイル名と CL オプションの後に表示する必要があります。 スペースは間で必要な **/link**と`linkeroptions`します。 詳細については、次を参照してください。 [MSVC リンカー参照](linking.md)します。

## <a name="example"></a>例

このサンプルのコマンドラインのコンパイル*hello.cpp*既存のオブジェクト ファイルにリンクと*there.obj*します。追加渡しますし **/VERSION**リンカー コマンド。

`cl /W4 /EHsc hello.cpp there.obj /link /VERSION:3.14`

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

IDE は、通常のコンパイルし、コードをリンクする個別のコマンドを送信します。 プロジェクトのプロパティ ページで、リンカー オプションを設定できます。

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)します。

1. 選択、**構成プロパティ** > **リンカー**フォルダー。

1. 1 つまたは複数のプロパティを変更します。 **OK** を選択して変更を保存してください。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- このコンパイラ オプションをプログラムで変更することはできません。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
