---
description: 詳細については、「」を参照してください。リンカー入力としての Lib ファイル
title: リンカー入力としての .lib ファイル
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.AdditionalDependencies
helpviewer_keywords:
- OMF libraries
- linking [C++], OMF libraries
- import libraries, linker files
- libraries [C++], .lib files as linker input
- COFF files, import libraries
- default libraries [C++], linker output
- default libraries [C++]
- defaults [C++], libraries
- .lib files
ms.assetid: dc5d2b1c-2487-41fa-aa71-ad1e0647958b
ms.openlocfilehash: f4a3b6c6487947772fb72135fb26f67857f0937e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201262"
---
# <a name="lib-files-as-linker-input"></a>リンカー入力としての .lib ファイル

リンクは COFF 標準ライブラリと COFF インポートライブラリを受け入れます。どちらも、通常拡張子 .lib を持ちます。 標準ライブラリにはオブジェクトが含まれており、LIB ツールによって作成されます。 インポートライブラリには、他のプログラムのエクスポートに関する情報が含まれており、エクスポートを含むプログラムまたは LIB ツールでビルドするときにリンクによって作成されます。 LIB を使用して標準ライブラリまたはインポートライブラリを作成する方法の詳細については、「 [Lib リファレンス](lib-reference.md)」を参照してください。 リンクを使用してインポートライブラリを作成する方法の詳細については、「 [/dll](dll-build-a-dll.md) オプション」を参照してください。

ファイル名引数または既定のライブラリのいずれかとしてリンクするライブラリが指定されています。 リンクを使用すると、コマンドラインで指定されたライブラリ、 [/DEFAULTLIB](defaultlib-specify-default-library.md) オプションで指定された既定のライブラリ、および .obj ファイル内の既定のライブラリで検索することで、外部参照を解決できます。 パスがライブラリ名と共に指定されている場合、リンクはそのディレクトリ内のライブラリを検索します。 パスが指定されていない場合は、リンクが実行されているディレクトリと、LIB 環境変数で指定されたディレクトリで、リンクが最初に表示されます。

## <a name="to-add-lib-files-as-linker-input-in-the-development-environment"></a>開発環境で .lib ファイルをリンカー入力として追加するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**リンカー** ] フォルダーの [**入力**] プロパティページをクリックします。

1. .Lib ファイルを追加するには、[ **追加の依存関係** プロパティを変更します。

## <a name="to-programmatically-add-lib-files-as-linker-input"></a>プログラムによって .lib ファイルをリンカー入力として追加するには

- 「 [Additionaldependencies](/dotnet/api/microsoft.visualstudio.vcprojectengine.vclinkertool.additionaldependencies)」を参照してください。

## <a name="example"></a>例

次のサンプルは、.lib ファイルをビルドして使用する方法を示しています。 まず、.lib ファイルをビルドします。

```cpp
// lib_link_input_1.cpp
// compile by using: cl /LD lib_link_input_1.cpp
__declspec(dllexport) int Test() {
   return 213;
}
```

次に、先ほど作成した .lib ファイルを使用して、このサンプルをコンパイルします。

```cpp
// lib_link_input_2.cpp
// compile by using: cl /EHsc lib_link_input_1.lib lib_link_input_2.cpp
__declspec(dllimport) int Test();
#include <iostream>
int main() {
   std::cout << Test() << std::endl;
}
```

```Output
213
```

## <a name="see-also"></a>関連項目

[リンク入力ファイル](link-input-files.md)<br/>
[MSVC リンカー オプション](linker-options.md)
