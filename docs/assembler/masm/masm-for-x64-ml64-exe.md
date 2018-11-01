---
title: x64 用 MASM (ml64.exe)
ms.date: 08/30/2018
helpviewer_keywords:
- ml64
- ml64.exe
- masm for x64
ms.assetid: 89059103-f372-4968-80ea-0c7f90bb9c91
ms.openlocfilehash: 0404bff54a08988a72fcb0a0c075a4446bf90f48
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596223"
---
# <a name="masm-for-x64-ml64exe"></a>x64 用 MASM (ml64.exe)

Visual Studio には、x64 を対象のコードを 32 ビットと 64 ビットの両方のホストされているバージョン Microsoft アセンブラー (MASM) にはが含まれています。 これは、x64 を受け入れるアセンブラー ml64.exe をという名前には、アセンブラー言語。 MASM のコマンド ライン ツールは、Visual Studio のインストール時に C++ ワークロードを選択するときにインストールされます。 MASM のツールでは、個別のダウンロードとして使用できません。 ダウンロードして Visual Studio のコピーをインストールする方法の詳細については、次を参照してください。 [Visual Studio のインストール](/visualstudio/install/install-visual-studio)します。 完全な Visual Studio IDE をインストールせずに、コマンド ライン ツールが欲しい、ダウンロード、 [Build Tools for Visual Studio 2017](https://go.microsoft.com/fwlink/p/?linkid=875721)します。

MASM を使用して構築するコマンド ラインでコードを x64 を対象と、x64 用開発者コマンド プロンプトを使用する必要がありますターゲットで、必要なパスとその他の環境変数を設定します。 開発者コマンド プロンプトを起動する方法については、次を参照してください。[コマンドラインでビルドの c/c++ コード](../../build/building-on-the-command-line.md)します。

Ml64.exe コマンド ライン オプションについては、次を参照してください。 [ML および ML64 のコマンド ライン リファレンス](../../assembler/masm/ml-and-ml64-command-line-reference.md)します。

X64 または ARM をターゲットには、インライン アセンブラーまたは ASM キーワードの使用がサポートされていません。 X86 コードを使用してインライン アセンブラーを移植する x64 または ARM では、c++ コードを変換、コンパイラ組み込み関数を使用したり、アセンブラー言語のソース ファイルを作成します。 Visual C コンパイラでは、例では、特権のあるビット スキャン/テスト、インタロックされたでとして可能なクロスプラット フォーム対応的に近いために、特別な関数の手順を使用することを許可する組み込み関数をサポートします。 使用可能な組み込み関数については、次を参照してください。[コンパイラ組み込み](../../intrinsics/compiler-intrinsics.md)します。

## <a name="add-an-assembler-language-file-to-a-visual-c-project"></a>アセンブラー言語ファイルを Visual C プロジェクトに追加します。

Visual Studio プロジェクト システムでは、C++ プロジェクトでの MASM を使用して構築されたアセンブラー言語ファイルをサポートします。 X64 アセンブラー言語のソース ファイルおよびオブジェクト ファイルを MASM x64 を完全にサポートを使用して作成を作成することができます。 X64 向けに構築された、C++ コードをこれらのオブジェクト ファイルをリンクすることができますし、対象とします。 これを x64 の欠如を克服する方法の 1 つは、インライン アセンブラー。

### <a name="to-add-an-assembler-language-file-to-an-existing-visual-c-project"></a>アセンブラー言語ファイルを既存の Visual C プロジェクトに追加するには

1. **ソリューション エクスプローラー**でプロジェクトを選択します。 メニュー バーで、**プロジェクト**、**ビルドのカスタマイズ**します。

1. **Visual C ビルド カスタマイズ ファイル** ダイアログ ボックスで、チェック ボックスを横に**masm(.targets,.props)** します。 選択**OK**選択内容を保存してダイアログ ボックスを閉じます。

1. メニュー バーで、**プロジェクト**、**新しい項目の追加**します。

1. **新しい項目の追加**ダイアログ ボックスで、 **C++ ファイル (.cpp)** 中央のウィンドウにします。 **名前**エディット コントロールを持つ新しいファイル名を入力、 **.asm** .cpp ではなく拡張機能。 選択**追加**ファイルをプロジェクトに追加し、ダイアログ ボックスを閉じます。

追加した .asm ファイルに、アセンブラー言語コードを作成します。 ソリューションをビルドする場合は、.asm ファイルをプロジェクトにリンクし、オブジェクト ファイルにアセンブルする MASM アセンブラーが呼び出されます。 シンボルへのアクセスを容易にするには、アセンブラー関数として宣言`extern "C"`を C++ ソース コードで、C++ を使用するのではなく名前装飾規約は、アセンブラー言語でソース ファイル。

## <a name="ml64-specific-directives"></a>ml64 固有のディレクティブ

X64 を対象とするアセンブラー言語ソース コードでは、ml64 固有の次のディレクティブを使用できます。

- [.ALLOCSTACK](../../assembler/masm/dot-allocstack.md)

- [.ENDPROLOG](../../assembler/masm/dot-endprolog.md)

- [.PUSHFRAME](../../assembler/masm/dot-pushframe.md)

- [.PUSHREG](../../assembler/masm/dot-pushreg.md)

- [.SAVEREG](../../assembler/masm/dot-savereg.md)

- [.SAVEXMM128](../../assembler/masm/dot-savexmm128.md)

- [.SETFRAME](../../assembler/masm/dot-setframe.md)

さらに、 [PROC](../../assembler/masm/proc.md)ディレクティブが ml64.exe で使用するために更新されました。

## <a name="32-bit-address-mode-address-size-override"></a>32 ビット アドレス モード (アドレス サイズ オーバーライド)

メモリ オペランドには、32 ビット レジスタが含まれている場合、MASM は 0x67 アドレス サイズのオーバーライドを生成します。 たとえば、次の例では、アドレス サイズのオーバーライドが生成されますが発生します。

```asm
mov rax, QWORD PTR [ecx]
mov eax, DWORD PTR [ecx*2+r10d]
mov eax, DWORD PTR [ecx*2+r10d+0100h]
prefetch [eax]
movnti rax, QWORD PTR [r8d]
```

MASM では、メモリのオペランドとして 32 ビットの変位が単独の場合は、64 ビットのアドレス指定ことを前提としています。 現在、このオペランドで 32 ビットのアドレス指定のサポートはありません。

最後に、次のコードに示すようにメモリ オペランドでは、レジスタのサイズが混在すると、エラーが発生します。

```asm
mov eax, DWORD PTR [rcx*2+r10d]
mov eax, DWORD PTR [ecx*2+r10+0100h]
```

## <a name="see-also"></a>関連項目

[Microsoft Macro Assembler リファレンス](../../assembler/masm/microsoft-macro-assembler-reference.md)<br/>