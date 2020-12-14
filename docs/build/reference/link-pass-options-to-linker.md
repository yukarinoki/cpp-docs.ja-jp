---
description: :/Link (リンカーにオプションを渡す) についての詳細情報
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
ms.openlocfilehash: 3617a005e6adbc41a589606aa145712fa2df442d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199494"
---
# <a name="link-pass-options-to-linker"></a>/link (リンカーにオプションを渡す)

リンカーに1つ以上のリンカーオプションを渡します。

## <a name="syntax"></a>構文

> **/link** *リンカー-オプション*

## <a name="arguments"></a>引数

*リンカー-オプション*<br/>
リンカーに渡されるリンカーオプションまたはオプション。

## <a name="remarks"></a>解説

**/Link** オプションとそのリンカーオプションは、任意のファイル名と CL オプションの後に指定する必要があります。 **/Link** オプションと任意のリンカーオプションの間にはスペースが必要です。 詳細については、「 [MSVC リンカーリファレンス](linking.md)」を参照してください。

## <a name="example"></a>例

このサンプルのコマンドラインでは、 *hello .cpp* がコンパイルされ、既存のオブジェクトファイルで *ある .obj* にリンクされます。次に、追加の **/VERSION** コマンドをリンカーに渡します。

`cl /W4 /EHsc hello.cpp there.obj /link /VERSION:3.14`

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

IDE は通常、個別のコマンドを送信してコードをコンパイルし、リンクします。 プロジェクトのプロパティページでリンカーオプションを設定できます。

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **構成プロパティ** の [リンカー] フォルダーを選択し  >  ます。

1. 1つまたは複数のプロパティを変更します。 **[OK]** を選択して変更を保存します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- このコンパイラオプションは、プログラムで変更することはできません。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
