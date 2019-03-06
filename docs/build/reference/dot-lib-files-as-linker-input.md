---
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
ms.openlocfilehash: f3b2ae0d82e682cc89243b7b527ee6e0b51d4c3d
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57426772"
---
# <a name="lib-files-as-linker-input"></a>リンカー入力としての .lib ファイル

リンクを受け入れる形式の標準ライブラリと COFF インポート ライブラリ、どちらも通常は拡張子が付いています。 lib します。 標準ライブラリでは、オブジェクトが含まれており、LIB ツールによって作成されます。 インポート ライブラリは、他のプログラムのエクスポートについての情報が含まれてし、エクスポートを含むプログラムをビルドするとき、またはライブラリをリンクするか作成します。 LIB を使用して、標準的な作成またはライブラリをインポートする方法の詳細については、次を参照してください。 [LIB リファレンス](../../build/reference/lib-reference.md)します。 リンクを使用して、インポート ライブラリを作成する方法の詳細については、次を参照してください。、 [/DLL](../../build/reference/dll-build-a-dll.md)オプション。

ライブラリは、ファイル名の引数または既定のライブラリのいずれかとしてリンクに指定されます。 リンクでは、外部参照を解決して、コマンドラインで指定されたライブラリを最初に検索し、ライブラリがで指定された既定の[/DEFAULTLIB](../../build/reference/defaultlib-specify-default-library.md)オプションで、既定のライブラリという名前の .obj ファイル内とします。 パスを指定するには、ライブラリ名を持つ、リンクはそのディレクトリでライブラリを検索します。 パスが指定されていない場合、リンクはリンクを実行しているディレクトリにし、その後、LIB 環境変数で指定されたディレクトリで検索します。

## <a name="to-add-lib-files-as-linker-input-in-the-development-environment"></a>開発環境でリンカー入力としての .lib ファイルを追加するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 選択、**入力**プロパティ ページで、**リンカー**フォルダー。

1. 変更、**追加の依存関係**.lib ファイルを追加するプロパティ。

## <a name="to-programmatically-add-lib-files-as-linker-input"></a>リンカー入力としての .lib ファイルをプログラムで追加するには

- 参照してください[AdditionalDependencies](/dotnet/api/microsoft.visualstudio.vcprojectengine.vclinkertool.additionaldependencies)します。

## <a name="example"></a>例

次の例では、ビルドし、.lib ファイルを使用する方法を示します。 .Lib ファイルを最初に、ビルドするには。

```cpp
// lib_link_input_1.cpp
// compile by using: cl /LD lib_link_input_1.cpp
__declspec(dllexport) int Test() {
   return 213;
}
```

作成した .lib ファイルを使用してこのサンプルをコンパイルします。

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

[LINK の入力ファイル](../../build/reference/link-input-files.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)
