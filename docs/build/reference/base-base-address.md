---
description: 詳細情報:/BASE (ベースアドレス)
title: /BASE (ベース アドレス)
ms.date: 09/05/2018
f1_keywords:
- /base
- VC.Project.VCLinkerTool.BaseAddress
helpviewer_keywords:
- base addresses [C++]
- programs [C++], preventing relocation
- semicolon [C++], specifier
- -BASE linker option
- key address size
- environment variables [C++], LIB
- programs [C++], base address
- LIB environment variable
- BASE linker option
- DLLs [C++], linking
- /BASE linker option
- '@ symbol for base address'
- executable files [C++], base address
- at sign symbol for base address
ms.assetid: 00b9f6fe-0bd2-4772-a69c-7365eb199069
ms.openlocfilehash: 269911c7d9fce47be1b9755ddebf38170ea4e81c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182776"
---
# <a name="base-base-address"></a>/BASE (ベース アドレス)

プログラムのベースアドレスを指定します。

## <a name="syntax"></a>構文

> **/Base:**{*address*[**,**<em>size</em>] | **\@**<em>filename</em>**、**<em>key</em>}

## <a name="remarks"></a>解説

> [!NOTE]
> セキュリティ上の理由から、実行可能ファイルのベースアドレスを指定するのではなく、 [/DYNAMICBASE](dynamicbase-use-address-space-layout-randomization.md) オプションを使用することをお勧めします。 これにより、Windows のアドレス空間レイアウトランダム化 (ASLR) 機能を使用して、読み込み時にランダムに再配置できる実行可能イメージが生成されます。 /DYNAMICBASE オプションは既定でオンになっています。

/BASE オプションは、プログラムのベースアドレスを設定して、.exe または DLL ファイルの既定の場所をオーバーライドします。 .Exe ファイルの既定のベースアドレスは、32ビットイメージの場合は0x400000、64ビットイメージの場合は0x140000000 です。 DLL の場合、既定のベースアドレスは32ビットイメージの場合は0x10000000、64ビットイメージの場合は0x180000000 です。 アドレス空間レイアウトのランダム化 (ASLR) をサポートしていないオペレーティングシステム、または/DYNAMICBASE: NO オプションが設定されている場合、オペレーティングシステムは最初に指定されたベースアドレスまたは既定のベースアドレスでプログラムの読み込みを試みます。 十分な領域がない場合は、システムによってプログラムが再配置されます。 再配置を防ぐには、 [/fixed](fixed-fixed-base-address.md) オプションを使用します。

*アドレス* が64k の倍数でない場合、リンカーはエラーを発行します。 必要に応じて、プログラムのサイズを指定することもできます。指定したサイズにプログラムが収まりきらない場合、リンカーは警告を発行します。

ベースアドレスを指定する別の方法としては、コマンドラインでベースアドレス応答ファイルを使用する方法があります。 ベースアドレス応答ファイルは、プログラムが使用するすべての Dll のベースアドレスとオプションのサイズ、およびベースアドレスごとに一意のテキストキーを含むテキストファイルです。 応答ファイルを使用してベースアドレスを指定するには、アットマーク ( **\@** ) の後に応答ファイル名、ファイル *名*、コンマ、コンマ、およびファイルで使用するベースアドレスの *キー* 値を続けて使用します。 リンカーは、LIB 環境変数で指定されたディレクトリに、指定されたパス、またはパスが指定されていない場合は、 *ファイル名* を検索します。 *Filename* の各行は1つの DLL を表し、次の構文があります。

> *キー* *アドレス* [*サイズ*] **;** *コメント*

*キー* は英数字の文字列であり、大文字と小文字は区別されません。 通常は DLL の名前ですが、である必要はありません。 *キー* の後に、C 言語、16進数、または10進表記のベース *アドレス* と、オプションの最大 *サイズ* が続きます。 3つの引数はすべて、スペースまたはタブで区切られます。 指定された *サイズ* がプログラムで必要な仮想アドレス空間よりも小さい場合、リンカーは警告を発行します。 *コメント* はセミコロン (**;**) で指定され、同じ行または別の行に配置できます。 リンカーは、セミコロンから行末までのすべてのテキストを無視します。 この例では、このようなファイルの一部を示します。

```
main   0x00010000    0x08000000    ; for PROJECT.exe
one    0x28000000    0x00100000    ; for DLLONE.DLL
two    0x28100000    0x00300000    ; for DLLTWO.DLL
```

これらの行を含むファイルを DLLS.txt と呼び出すと、次のコマンドの例でこの情報が適用されます。

```
link dlltwo.obj /dll /base:@dlls.txt,two
```

ベースアドレスを設定するもう1つの方法は、 [NAME](name-c-cpp.md)または [LIBRARY](library.md)ステートメントで *base* 引数を使用することです。 /BASE オプションと [/dll](dll-build-a-dll.md) オプションを一緒に使うことは、 **LIBRARY** ステートメントと同じです。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**]  >  **リンカー** の  >  **[詳細設定**] プロパティページを選択します。

1. **ベースアドレス** プロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.BaseAddress%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
