---
title: X64 用 MASM (ml64.exe) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/21/2018
ms.technology:
- cpp-masm
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ml64
- ml64.exe
- masm for x64
ms.assetid: 89059103-f372-4968-80ea-0c7f90bb9c91
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bb4f4a0ba996be34749350c0d99c1915752fe99e
ms.sourcegitcommit: e013acba70aa29fed60ae7945162adee23e19c3b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/22/2018
ms.locfileid: "36322249"
---
# <a name="masm-for-x64-ml64exe"></a>x64 用 MASM (ml64.exe)

Visual Studio には、x64 を対象のコードを 32 ビットおよび 64 ビットの両方のホストされているバージョン Microsoft アセンブラー (MASM) にはが含まれています。 これは、x64 を受け入れるアセンブラー ml64.exe をという名前には、アセンブラー言語。 MASM のコマンド ライン ツールは、Visual Studio のインストール時に C++ ワークロードを選択するときにインストールされます。 MASM ツールは、個別のダウンロードとしてご利用いただけません。 ダウンロードして Visual Studio のコピーをインストールする方法については、次を参照してください。 [Visual Studio インストール](/visualstudio/install/install-visual-studio)です。 完全な Visual Studio IDE をインストールせずにのみするには、コマンド ライン ツール、ダウンロード、[構築ツールを Visual Studio 2017 の](https://go.microsoft.com/fwlink/p/?linkid=875721)します。

ビルドに MASM を使用する x64 用のコードをコマンドラインでターゲットを x64 用開発者コマンド プロンプトを使用する必要がありますターゲットで、必要なパスとその他の環境変数を設定します。 開発者コマンド プロンプトを起動する方法については、次を参照してください。[コマンドラインでビルドの c/c++ コード](../../build/building-on-the-command-line.md)です。

Ml64.exe コマンド ライン オプションについては、次を参照してください。 [ML および ML64 のコマンド ライン リファレンス](../../assembler/masm/ml-and-ml64-command-line-reference.md)です。  
  
X64、または ARM を対象には、インライン アセンブラーまたは ASM キーワードの使用がサポートされていません。 X86 を使用してインライン アセンブラーのコードに移植する x64 または ARM の場合は、c++ コードを変換、コンパイラの組み込み関数を使用したり、アセンブラー言語ソース ファイルを作成します。 Visual C コンパイラでは、例では、特権のあるビットのスキャン/テスト、インタロックされたでとして可能なクロスプラット フォームの形に近いために特別な関数の手順を使用することを許可する組み込み関数をサポートします。 使用可能な組み込み関数については、次を参照してください。[コンパイラの組み込み](../../intrinsics/compiler-intrinsics.md)です。  

## <a name="add-an-assembler-language-file-to-a-visual-c-project"></a>アセンブラー言語ファイルを Visual C プロジェクトに追加します。  
  
Visual Studio プロジェクト システムでは、C++ プロジェクトでの MASM を使用してビルドされたアセンブラー言語ファイルをサポートします。 X64 アセンブラー言語のソース ファイルし、x64 を完全にサポートする MASM を使用してそれらをオブジェクト ファイルにビルドを作成することができます。 X64 用にビルドされた C++ コードに、これらのオブジェクト ファイルをリンクすることができますし、ターゲットです。 これを x64 の不足を解決する方法の 1 つは、インライン アセンブラーです。  

### <a name="to-add-an-assembler-language-file-to-an-existing-visual-c-project"></a>既存の Visual C プロジェクトに、アセンブラー言語ファイルを追加するには

1. プロジェクトを選択**ソリューション エクスプ ローラー**です。 メニュー バーで、次のように選択します。**プロジェクト**、**ビルド カスタマイズ**です。

1. **Visual C ビルド カスタマイズ ファイル** ダイアログ ボックスで、チェック ボックスを横に**masm(.targets,.props)** です。 選択**OK**選択内容を保存してダイアログ ボックスを閉じます。

1. メニュー バーで、次のように選択します。**プロジェクト**、**新しい項目の追加**です。 

1. **新しい項目の追加**ダイアログ ボックスで、 **C++ ファイル (.cpp)** 中央のペインでします。 **名前**エディット コントロールを持つ新しいファイル名を入力、 **.asm** .cpp の代わりに拡張します。 選択**追加**ファイルをプロジェクトに追加し、ダイアログ ボックスを閉じます。

追加した .asm ファイルに、アセンブラー言語コードを作成します。 ソリューションをビルドするときに、プロジェクトに、リンクされているオブジェクト ファイルに .asm ファイルをアセンブルする MASM アセンブラーが呼び出されます。 シンボルへのアクセスを容易にするには、宣言、アセンブラー関数として`extern "C"`C++ ソース コードで C++ を使用するのではなく名前装飾規約は、アセンブラー言語でソース ファイルです。
  
## <a name="ml64-specific-directives"></a>ml64 固有のディレクティブ  

X64 を対象とするアセンブラー言語ソース コードでは、ml64 固有の次のディレクティブを使用できます。  
  
-   [.ALLOCSTACK](../../assembler/masm/dot-allocstack.md)  
  
-   [.ENDPROLOG](../../assembler/masm/dot-endprolog.md)  
  
-   [.PUSHFRAME](../../assembler/masm/dot-pushframe.md)  
  
-   [.PUSHREG](../../assembler/masm/dot-pushreg.md)  
  
-   [.SAVEREG](../../assembler/masm/dot-savereg.md)  
  
-   [.SAVEXMM128](../../assembler/masm/dot-savexmm128.md)  
  
-   [.SETFRAME](../../assembler/masm/dot-setframe.md)  
  
さらに、 [PROC](../../assembler/masm/proc.md) ml64.exe で使用するディレクティブが更新されました。  
  
## <a name="32-bit-address-mode-address-size-override"></a>32 ビット アドレス モード (アドレス サイズ オーバーライド)  

メモリ オペランドには、32 ビット レジスタが含まれている場合、MASM は 0x67 アドレス サイズ オーバーライドを出力します。 たとえば、次の例では、アドレスのサイズのオーバーライドが生成されますが発生します。  
  
```MASM  
mov rax, QWORD PTR [ecx]  
mov eax, DWORD PTR [ecx*2+r10d]  
mov eax, DWORD PTR [ecx*2+r10d+0100h]  
prefetch [eax]  
movnti rax, QWORD PTR [r8d]  
```  
  
MASM では、32 ビットの変位がメモリ オペランドとして単独で表示された場合は 64 ビットのアドレス指定がものであると仮定します。 現在、このオペランドでアドレス指定 32 ビットのサポートはありません。  
  
最後に、次のコードに示すようにメモリ オペランド内のレジスタ サイズを混在させると、エラーが発生します。  
  
```MASM  
mov eax, DWORD PTR [rcx*2+r10d]  
mov eax, DWORD PTR [ecx*2+r10+0100h]  
```  
  
## <a name="see-also"></a>関連項目  

[Microsoft Macro Assembler リファレンス](../../assembler/masm/microsoft-macro-assembler-reference.md)