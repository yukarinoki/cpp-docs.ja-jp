---
title: ベース (ベース アドレス) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /base
- VC.Project.VCLinkerTool.BaseAddress
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c4090a3e8d2f9f3bdcb68875d94a1b84e7bff0f3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376625"
---
# <a name="base-base-address"></a>/BASE (ベース アドレス)
```  
/BASE:{address[,size] | @filename,key}  
```  
  
 基本オプションは、.exe または DLL ファイルの既定の場所をオーバーライドして、プログラムのベース アドレスを設定します。 .Exe ファイルの既定のベース アドレスは、32 ビットのイメージ 0x400000 または 64 ビットのイメージ 0x140000000 です。 Dll の場合、既定のベース アドレスは、32 ビットのイメージ 0x10000000 または 64 ビットのイメージ 0x180000000 です。 アドレス space layout randomization (機能) をサポートしていないか、/DYNAMICBASE:NO オプションが設定されたときのオペレーティング システムで、オペレーティング システムは、最初に指定されたプログラムまたは既定のベース アドレスをロードを試みます。 十分な空き領域がない使用可能な場合、システムには、プログラムが再配置します。 再配置を防ぐためを使用して、 [固定/](../../build/reference/fixed-fixed-base-address.md)オプション。  
  
 場合、リンカーはエラー*アドレス*64 K の倍数ではありません。 必要に応じて、プログラムのサイズを指定することができます。リンカーは、プログラムが指定したサイズに収まらない場合に警告を発行します。  
  
 コマンド ラインでは、ベース アドレスを指定する別の方法は、ベース アドレスの応答ファイルを使用してです。 ベース アドレスの応答ファイルは、ベース アドレスと、プログラムで使用すると、すべての Dll と基本アドレスごとに固有のテキストをキーの省略可能なサイズを含むテキスト ファイルです。 応答ファイルを使用してベース アドレスを指定するには、使用、アット マーク (@) 応答ファイルの名前を続けて*filename*、コンマ、その後に、`key`ファイルで使用するベース アドレスの値。 リンカー *filename*いずれかを指定したパスでパスを指定しない場合、LIB 環境変数で指定したディレクトリ内、または。 内の各行*filename* 1 つの DLL を表し、次の構文を持ちます。  
  
```  
  
key address [size] ;comment  
```  
  
 `key`文字の英数字の文字列は、大文字小文字を区別します。 通常、DLL の名前ですが、必要はありません。 `key`ベースが続く*アドレス*C 言語、16 進数、または 10 進表記で省略可能な最大`size`です。 3 つの引数は、スペースまたはタブで区切られます。 リンカー警告を発行、指定した`size`が、プログラムに必要な仮想アドレス空間よりも小さいです。 A`comment`セミコロン (;) で指定され、同一または別の行を指定できます。 リンカーは、行の末尾にセミコロンからすべてのテキストを無視します。 この例では、このようなファイルの一部を示します。  
  
```  
main   0x00010000    0x08000000    ; for PROJECT.exe  
one    0x28000000    0x00100000    ; for DLLONE.DLL  
two    0x28100000    0x00300000    ; for DLLTWO.DLL  
```  
  
 これらの行を格納しているファイルには、DLLS.txt が呼び出されるとは、次のコマンド例には、この情報が適用されます。  
  
```  
link dlltwo.obj /dll /base:@dlls.txt,two  
```  
  
## <a name="remarks"></a>コメント  
 セキュリティ上の理由から、使用するをお勧めします。、 [/DYNAMICBASE](../../build/reference/dynamicbase-use-address-space-layout-randomization.md)オプションは、実行可能ファイルのベース アドレスを指定する代わりにします。 これには、ランダムにリベースできる読み込み時に Windows の address space layout randomization (機能) 機能を使用して、実行可能イメージが生成されます。 /DYNAMICBASE オプションは、既定では、オンです。  
  
 ベース アドレスを設定する別の方法を使用して、*基本*の引数、[名前](../../build/reference/name-c-cpp.md)または[ライブラリ](../../build/reference/library.md)ステートメントです。 /BASE と[/DLL](../../build/reference/dll-build-a-dll.md)オプションは一緒に相当する、**ライブラリ**ステートメントです。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  展開して、**リンカー**フォルダーです。  
  
3.  選択、**詳細**プロパティ ページ。  
  
4.  変更、**のベース アドレス**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.BaseAddress%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)