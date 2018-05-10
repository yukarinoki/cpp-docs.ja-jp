---
title: Visual C++ ツールセットで問題を報告する方法 | Microsoft Docs
ms.date: 1/11/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e8be0a5e42caf12c4e1415cf88143b84a9971cd2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-report-a-problem-with-the-visual-c-toolset"></a>Visual C++ ツールセットで問題を報告する方法

Microsoft Visual C++ のコンパイラ、リンカー、その他のツールとライブラリを使っていて問題が発生した場合は、Microsoft にお知らせください。

問題についてのご連絡に最適な方法は、発生した問題の説明、プログラムの作成方法の詳細、および Microsoft のコンピューターで問題を再現するために使うことができる*再現コード*、完全なテスト ケースを含む、レポートをお送りいただくことです。 この情報があると、短時間で、Microsoft のコードに問題が存在していて、報告者の環境だけの問題ではないことを確認すること、また、コンパイラの他のバージョンに影響があるかどうかを特定して、原因を診断することができます。

このドキュメントでは、次のことについて説明します。

- [レポートを準備する方法](#how-to-prepare-your-report)、および優れたレポートの内容。

- [再現コードを生成する方法](#how-to-generate-a-repro)、および再現コードのさまざまな種類。

- [レポートを送信する方法](#ways-to-send-your-report)、およびそれぞれの違い。

レポートは、Microsoft にとっても他の開発者にとっても重要です。 Visual C++ の向上にご協力いただきありがとうございます。

## <a name="how-to-prepare-your-report"></a>レポートを準備する方法

完全な情報がないと Microsoft のコンピューターで問題を再現するのはとても困難なので、質の高いレポートを作成することが重要です。 レポートの質がよいほど、より効果的に問題を再現して診断できます。

レポートには少なくとも次の情報を含める必要があります。

- 使っているツールセットの完全なバージョン情報。

- コードをビルドするために使った完全な cl.exe コマンド ライン。

- 発生した問題の詳細な説明。

- 再現コードは、問題を実際に示す完全な簡素化された自己完結型のソース コード例です。

具体的に必要な情報およびそれが見つかる場所、および最適な再現コードの作成方法については以下で説明します。

### <a name="the-toolset-version"></a>ツールセットのバージョン

Microsoft のコンピューターで同じツールセットに対して再現コードをテストできるように、問題を引き起こすツールセットの完全なバージョン情報とターゲット アーキテクチャが必要です。 問題を再現できる場合、この情報を基にして同じ問題が発生するツールセットの他のバージョンを調査できます。

#### <a name="to-report-the-full-version-of-the-compiler-youre-using"></a>使っているコンパイラの完全バージョンを報告するには

1. プロジェクトをビルドするために使用した Visual Studio のバージョンと構成アーキテクチャに一致する**開発者コマンド プロンプト**を開きます。 たとえば、x64 ターゲットに対して、x64 で Visual Studio 2017 を使用してビルドする場合は、**VS 2017 用の x64 Native Tools コマンド プロンプト**を選びます。 詳細については、[開発者コマンド プロンプトのショートカット](build/building-on-the-command-line.md#developer-command-prompt-shortcuts)に関するトピックを参照してください。

1. 開発者コマンド プロンプト コンソール ウィンドウで、コマンド **cl** を入力します。

出力は次のようになります。

```Output
C:\Users\username\Source>cl
Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x64
Copyright (C) Microsoft Corporation.  All rights reserved.

usage: cl [ option... ] filename... [ /link linkoption... ]
```

出力全体をコピーして、レポートに貼り付けます。

### <a name="the-command-line"></a>コマンド ライン

Microsoft のコンピューターでコードをまったく同じ方法でビルドできるように、コードのビルドに使ったのと同じコマンド ライン (cl.exe とそのすべての引数) が必要です。 これは、特定の引数または引数の組み合わせを使ってビルドしたときにのみ問題が発生する可能性があるので重要です。

この情報を検索する最適な場所は、問題が発生した直後のビルド ログです。 このようにすると、問題の原因となった可能性があるまったく同じ引数がコマンド ラインに確実に含まれます。

#### <a name="to-report-the-contents-of-the-command-line"></a>コマンド ラインの内容を報告するには

1. **CL.command.1.tlog** ファイルを探して開きます。 既定では、このファイルは、\\Visual Studio *version*\\Projects\\*SolutionName*\\*ProjectName*\\*Configuration*\\*ProjectName*.tlog\\CL.command.1.tlog 内のドキュメント フォルダー内、または \\Source\\Repos\\*SolutionName*\\*ProjectName*\\*Configuration*\\*ProjectName*.tlog\\CL.command.1.tlog の下のご自分のユーザー フォルダー内にあります。 別のビルド システムを使用している場合、またはプロジェクトの既定の場所を変更した場合は、別の場所にある可能性があります。

   このファイルで、ソース コード ファイルの名前と、コンパイルに使われたコマンド ライン引数を探します。これらは別々の行になっています。

1. 問題が発生したソース コード ファイルの名前を含む行を探します。その下の行には、対応する cl.exe コマンド引数が含まれています。

コマンド ライン全体をコピーして、レポートに貼り付けます。

### <a name="a-description-of-the-problem"></a>問題の説明

弊社のコンピューターで同じ結果を見ていることを確認できるように、問題の詳細な説明が必要です。また、実行しようとしていたこと、および予想された結果をお知らせいただくと、役に立つ場合があります。

ツールセットで表示する正確なエラー メッセージ、または表示される正確な実行時の動作を指定します。 この情報は、問題が正しく再現されたことを Microsoft が確認するために必要です。 最後のエラー メッセージだけでなく、すべてのコンパイラ出力を含めてください。 Microsoft では、報告する問題が発生するまでのすべてのことを確認する必要があります。 コマンド ライン コンパイラを使用して問題を複製できる場合は、そのコンパイラの出力が推奨されます。IDE およびその他のビルド システムは、表示されるエラー メッセージがフィルター処理されたり、エラー メッセージの最初の行のみがキャプチャされたりする場合があります。

コンパイラが無効なコードを受け入れ、診断を生成しないことが問題の場合、このことをレポートに記載してください。

実行時の動作の問題を報告するには、プログラムで出力されたものの正確なコピーと、表示されるべきものを含めます。 たとえば `printf("This should be 5: %d\n", actual_result);` のように、これが出力ステートメントそのものに含まれているのが理想的です。 プログラムがクラッシュまたはハングする場合は、そのことも記載してください。

発生した問題の診断に役立つ可能性があるその他の詳細 (自分で見つけた回避策など) を追加します。 レポートの別の場所にある情報を繰り返し記載しないでください。

### <a name="the-repro"></a>再現コード

再現コードは、再現可能な方法で発生している問題を示す、完全な自己完結型のソース コード例です (これが名前の由来です)。 再現コードは、Microsoft のコンピューターでエラーを再現できるようにするために必要です。 コードは、それだけでコンパイルして実行する、または見つかった問題がなければ、コンパイルして実行できたはずの単純な実行可能ファイルを作成するのに十分である必要があります。 再現コードはコード スニペットではありません。完全な関数とクラスがあり、標準のヘッダーに対しても、必要なすべての #include ディレクティブが含まれている必要があります。

#### <a name="what-makes-a-good-repro"></a>適切な再現コードを作成には

適切な再現コード:

- **最小限である**。 再現コードは、発生した問題を正確に再現しながら、可能な限り小さくする必要があります。 再現コードは複雑または現実的なものである必要はありません。必要なのは、標準または文書化されているコンパイラの実装に準拠しているコード、または診断が存在しない場合は、適合しないコードを示すことだけです。 問題を再現するのに十分なコードを含むシンプルで的を射た再現コードが最適です。 準拠した状態を保ち、さらに問題を変更せずに、コードを除去または簡素化できる場合は、そのようにしてください。 動作するコードの反例を含める必要はありません。

- **自己完結的である**。 再現手順には、必要のない依存関係を含めないようにする必要があります。 サード パーティ製のライブラリがなくても問題を再現できる場合は、使わずに再現してください。 単純な出力ステートメントだけでなく、ライブラリ コードがなくても、問題を再現できる場合は (たとえば、`puts("this shouldn't compile");`、`std::cout << value;`、`printf("%d\n", value);` は大丈夫です)、そのようにしてください。 これは、ユーザー ヘッダーへの参照なしで例を 1 つのソース コード ファイルに凝縮できる場合に最適です。 問題の可能性のある原因として考える必要のあるコードの量を減らすことは、調査するときにとても役に立ちます。

- **最新バージョンのコンパイラが対象である**。 再現コードは、最新バージョンのツールセットの最新の更新プログラム、または可能な場合には常に、次回の更新プログラムまたは次のメジャー リリースの最新のプレリリース版を使用する必要があります。 古いバージョンのツールセットで発生する問題の多くは、新しいバージョンで修正されています。 修正プログラムが以前のバージョンに移植されるのは、例外的な状況でだけです。

- **他のコンパイラで確認されている** (関連する場合)。 移植可能な C++ コードに関係のある再現手順は、可能であれば、他のコンパイラで動作を確認する必要があります。 標準は、プログラムの正確性を最終的に判断します。完全なコンパイラはありませんが、Clang と GCC が診断なしでコードを受け入れ、MSVC が受け入れない場合は、お使いのコンパイラのバグを見ている可能性があります  (その他の可能性として、UNIX と Windows の動作の違いや、C++ の標準実装のレベルの違いなどがあります)。一方、すべてのコンパイラがコードを拒否する場合は、コードが間違っている可能性があります。 さまざまなエラー メッセージを見ることで、自分で問題を診断できる場合があります。

   コードをテストするオンライン コンパイラのリストは、ISO C++ Web サイトの[オンライン C++ コンパイラ](https://isocpp.org/blog/2013/01/online-c-compilers)、または GitHub の選別された[オンライン C++ コンパイラのリスト](https://arnemertz.github.io/online-compilers/)で見つけることができます。 具体的な例には、[Wandbox](https://wandbox.org/)、[Compiler Explorer](https://godbolt.org/)、[Coliru](http://coliru.stacked-crooked.com/) などがあります。

   > [!NOTE]
   > オンライン コンパイラの Web サイトは Microsoft とは関係ありません。 オンライン コンパイラの Web サイトの多くは、個人のプロジェクトとして運営されており、これを読んでいる時点で閲覧できなくなっているサイトもあるかもしれませんが、検索すれば、その他の使用できるサイトが見つかるはずです。

コンパイラ、リンカー、ライブラリの問題は、特定の方法で発生する傾向があります。 発生した問題の種類により、レポートに含める必要がある再現コードの種類が決まります。 適切な再現コードがないと、調査するものがありません。 発生する可能性のあるいくつかの問題の種類と、問題の種類ごとにレポートに使用する必要のある再現コードの種類の生成の手順を次に示します。

#### <a name="frontend-parser-crash"></a>フロントエンド (パーサー) のクラッシュ

フロントエンドのクラッシュは、コンパイラの解析フェーズの間に発生します。 通常、コンパイラは、[致命的なエラー C1001](error-messages/compiler-errors-1/fatal-error-c1001.md) を出力し、エラーが発生したソース コード ファイルと行番号を参照します。ファイル msc1.cpp が言及されていることがよくありますが、この詳細は無視してかまいません。

この種のクラッシュの場合は、[前処理済み再現コード](#preprocessed-repros)を提供してください。

この種のクラッシュに対するコンパイラ出力の例を次に示します。

```Output
SandBoxHost.cpp
d:\o\dev\search\foundation\common\tools\sandbox\managed\managed.h(929):
        fatal error C1001: An internal error has occurred in the compiler.
(compiler file 'msc1.cpp', line 1369)
To work around this problem, try simplifying or changing the program near the
        locations listed above.
Please choose the Technical Support command on the Visual C++
Help menu, or open the Technical Support help file for more information
d:\o\dev\search\foundation\common\tools\sandbox\managed\managed.h(929):
        note: This diagnostic occurred in the compiler generated function
        'void Microsoft::Ceres::Common::Tools::Sandbox::SandBoxedProcess::Dispose(bool)'
Internal Compiler Error in d:\o\dev\otools\bin\x64\cl.exe.  You will be prompted
        to send an error report to Microsoft later.
INTERNAL COMPILER ERROR in 'd:\o\dev\otools\bin\x64\cl.exe'
    Please choose the Technical Support command on the Visual C++
    Help menu, or open the Technical Support help file for more information
```

#### <a name="backend-code-generation-crash"></a>バックエンド (コード生成) のクラッシュ

バックエンドのクラッシュは、コンパイラのコード生成フェーズの間に発生します。 通常、コンパイラは、[致命的なエラー C1001](error-messages/compiler-errors-1/fatal-error-c1001.md) を出力し、問題に関連するソース コード ファイルと行番号を参照していない場合があります。ファイル compiler\\utc\\src\\p2\\main.c が言及されていることがよくありますが、この詳細は無視してかまいません。

この種のクラッシュの場合は、**/GL** コマンド ライン引数を cl.exe に指定することによって有効したリンク時のコード生成 (LTCG) を使っている場合は、[リンク再現コード](#link-repros)を提供してください。 使っていない場合は、代わりに[前処理済み再現コード](#preprocessed-repros)を提供してください。

LTCG を使っていないバックエンド クラッシュに対するコンパイラ出力の例を次に示します。 このようなコンパイラ出力の場合は、[前処理済み再現コード](#preprocessed-repros)を提供する必要があります。

```Output
repro.cpp
\\officefile\public\tadg\vc14\comperror\repro.cpp(13) : fatal error C1001:
        An internal error has occurred in the compiler.
(compiler file 'f:\dd\vctools\compiler\utc\src\p2\main.c', line 230)
To work around this problem, try simplifying or changing the program near the
        locations listed above.
Please choose the Technical Support command on the Visual C++
Help menu, or open the Technical Support help file for more information
INTERNAL COMPILER ERROR in
        'C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\BIN\cl.exe'
    Please choose the Technical Support command on the Visual C++
    Help menu, or open the Technical Support help file for more information
```

**内部コンパイラ エラー**で始まる行において、cl.exe ではなく link.exe が言及されている場合は、LTCG が有効になっていたので、[リンク再現手順](#link-repros)を提供する必要があります。 コンパイラのエラー メッセージから LTCG が有効になっていたどうかはっきりわからない場合は、前の手順で **/GL** コマンド ライン引数に対するビルド ログからコピーしたコマンド ライン引数を調べることが必要な場合があります。

#### <a name="linker-crash"></a>リンカーのクラッシュ

リンカーのクラッシュは、コンパイラが実行された後のリンク フェーズ中に発生します。 通常、リンカーは[リンカー ツール エラー LNK1000](error-messages/tool-errors/linker-tools-error-lnk1000.md) を出力します。

> [!NOTE]
> 出力が C1001 またはリンク時コード生成に関するものである場合は、「[バックエンド (コード生成) のクラッシュ](#backend-code-generation-crash)」で詳細をご覧ください。

この種のクラッシュの場合は、[リンク再現コード](#link-repros)を提供してください。

この種のクラッシュに対するコンパイラ出力の例を次に示します。

```Output
z:\foo.obj : error LNK1000: Internal error during IMAGE::Pass2

  Version 14.00.22816.0

  ExceptionCode            = C0000005
  ExceptionFlags           = 00000000
  ExceptionAddress         = 00007FF73C9ED0E6 (00007FF73C9E0000)
        "z:\tools\bin\x64\link.exe"
  NumberParameters         = 00000002
  ExceptionInformation[ 0] = 0000000000000000
  ExceptionInformation[ 1] = FFFFFFFFFFFFFFFF

CONTEXT:

  Rax    = 0000000000000400  R8     = 0000000000000000
  Rbx    = 000000655DF82580  R9     = 00007FF840D2E490
  Rcx    = 005C006B006F006F  R10    = 000000655F97E690
  Rdx    = 000000655F97E270  R11    = 0000000000000400
  Rsp    = 000000655F97E248  R12    = 0000000000000000
  Rbp    = 000000655F97EFB0  E13    = 0000000000000000
  Rsi    = 000000655DF82580  R14    = 000000655F97F390
  Rdi    = 0000000000000000  R15    = 0000000000000000
  Rip    = 00007FF73C9ED0E6  EFlags = 0000000000010206
  SegCs  = 0000000000000033  SegDs  = 000000000000002B
  SegSs  = 000000000000002B  SegEs  = 000000000000002B
  SegFs  = 0000000000000053  SegGs  = 000000000000002B
  Dr0    = 0000000000000000  Dr3    = 0000000000000000
  Dr1    = 0000000000000000  Dr6    = 0000000000000000
  Dr2    = 0000000000000000  Dr7    = 0000000000000000
```

インクリメンタル リンクが有効になっていて、初期リンクが成功、つまり後続のインクリメンタル リンクの基になっている最初のフル リンクの後でのみクラッシュが発生する場合は、初期リンクが完了した後で変更されたソース ファイルに対応するオブジェクト (.obj) ファイルとライブラリ (.lib) ファイルのコピーも提供してください。

#### <a name="bad-code-generation"></a>不正なコードの生成

不正なコードが生成されることはまれですが、コンパイラが誤って不適切なコードを生成し、アプリケーションがコンパイル時にこの問題を検出せずに実行時にクラッシュすると発生します。 発生している問題が不正なコードの生成の結果であると考えられる場合は、[バックエンド (コード生成) のクラッシュ](#backend-code-generation-crash)と同じようにレポートを処理してください。

この種のクラッシュの場合は、**/GL** コマンド ライン引数を cl.exe に指定することによって有効したリンク時のコード生成 (LTCG) を使っている場合は、[リンク再現コード](#link-repros)を提供してください。 使っていない場合は、[前処理済み再現コード](#preprocessed-repros)を提供してください。

## <a name="how-to-generate-a-repro"></a>再現コードの生成方法

Microsoft での問題の原因究明には、[適切な再現コード](#what-makes-a-good-repro)が非常に重要です。 特定の種類の再現コードについて、以下で説明する手順を実行する前に、問題を示すコードをできる限り凝縮してください。 依存関係、必須のヘッダー、ライブラリを除去または最小化し、可能な場合には使用したコンパイラ オプションとプリプロセッサ定義を制限します。

異なる種類の問題の報告に使うさまざまな種類の再現コードを生成する手順を次に示します。

### <a name="preprocessed-repros"></a>前処理済み再現コード

*前処理済みの再現コード*は、問題を示す単一のソース ファイルで、元の再現コードのソース ファイルで **/P** コンパイラ オプションを使用することで、C プリプロセッサの出力から生成されます。 これにより、インクルードされているヘッダーがインライン化されて他のソース ファイルとヘッダー ファイルへの依存関係が削除され、ローカル環境に依存する可能性のあるマクロ、#ifdefs、その他のプリプロセッサ コマンドも解決されます。

> [!NOTE]
> 問題の原因が標準ライブラリの実装におけるバグの可能性がある場合、通常、問題が解決済みかどうかを確認するために最新の作業中の実装に置き換えるので、前処理済みの再現コードはあまり役に立ちません。 この場合は、再現コードを前処理しないでください。また、問題を 1 つのソース ファイルに減らすことができない場合は、コードを .zip ファイルなどにパッケージ化するか、IDE プロジェクトの再現コードの使用を検討してください。 詳細については、「[その他の再現コード](#other-repros)」を参照してください。

#### <a name="to-preprocess-a-source-code-file"></a>ソース コード ファイルを前処理するには

1. 「[コマンド ラインの内容を報告するには](#to-report-the-contents-of-the-command-line)」の説明に従って、再現コードをビルドするために使用したコマンド ライン引数をキャプチャします。

1. プロジェクトをビルドするために使用した Visual Studio のバージョンと構成アーキテクチャに一致する**開発者コマンド プロンプト**を開きます。

1. 再現コード プロジェクトを含むディレクトリに移動します。

1. 開発者コマンド プロンプト コンソール ウィンドウで、コマンド **cl /P** *arguments* *filename.cpp* を入力します。ここで、*arguments* は、上でキャプチャした引数のリストで、*filename.cpp* は再現コードのソース ファイルの名前です。 このコマンドは、再現コードに使用したコマンド ラインをレプリケートしますが、プリプロセッサ パスの後、コンパイルを停止し、前処理済みのソース コードを *filename*.i に出力します。

ファイルを前処理済みのファイルを生成したら、そのファイルを使用して問題が引き続き再現されることを確認してください。

#### <a name="to-confirm-that-the-error-still-repros-with-the-preprocessed-file"></a>前処理済みファイルでエラーが再現することを確認するには

1. 開発者コマンド プロンプト コンソール ウィンドウで、コマンド **cl** *arguments* **/TP** *filename***.i** を入力して、cl.exe に前処理済みのファイルを C++ ソース ファイルとしてコンパイルするように指示します。ここで、*arguments* は上でキャプチャした引数のリストですが、**/D** 引数と **/I** 引数は、前処理済みのファイルに既に含まれているため削除されています。*filename * * * .i** は、前処理済みファイルの名前です。

1. 問題が再現することを確認します。

最後に、前処理済みの再現コード *filename*.i を自分のレポートに添付します。

### <a name="link-repros"></a>リンク再現コード

*リンク再現コード*は、**link\_repro** 環境変数で指定されたリンカーによって生成されたディレクトリ内容です。 これには、リンク時コード生成 (LTCG) が関係するバックエンド クラッシュやリンカー クラッシュなど、リンク時に発生する問題を全体として再現するビルド成果物が含まれます。 これらのビルド成果物は、問題が再現できるように、リンカー入力として必要なものです。 リンク再現コードは、この環境変数を使用して、リンカーの組み込みの再現コード生成機能を有効にすることで簡単に作成できます。

#### <a name="to-generate-a-link-repro"></a>リンク再現コードを生成するには

1. 「[コマンド ラインの内容を報告するには](#to-report-the-contents-of-the-command-line)」の説明に従って、再現コードをビルドするために使用したコマンド ライン引数をキャプチャします。

1. プロジェクトをビルドするために使用した Visual Studio のバージョンと構成アーキテクチャに一致する**開発者コマンド プロンプト**を開きます。

1. 開発者コマンド プロンプト コンソール ウィンドウで、自分の再現コード プロジェクトが含まれているディレクトリに移動します。

1. **mkdir linkrepro** を入力して、リンク再現コードのディレクトリを作成します。

1. コマンド **set link\_repro=linkrepro** を入力して、作成したディレクトリに **link\_repro** 環境変数を設定します。

1. Visual Studio で再現コード プロジェクトをビルドするには、開発者コマンド プロンプト コンソール ウィンドウで、コマンド **devenv** を入力します。 これにより、**link\_repro** 環境変数の値を Visual Studio で認識できるようになります。 コマンド ラインでプロジェクトをビルドするには、上でキャプチャしたコマンド ライン引数を使用して再現コード ビルドを複製します。

1. 再現コード プロジェクトをビルドし、予想された問題が発生することを確認します。

1. Visual Studio を閉じます (ビルドの実行に使用した場合)。

1. 開発者コマンド プロンプト コンソール ウィンドウで、コマンド **set link\_repro=** を入力して、**link\_repro** 環境変数をクリアします。

最後に、linkrepro ディレクトリ全体を .zip ファイルなどに圧縮することで再現コードをパッケージ化し、レポートに添付します。

### <a name="other-repros"></a>その他の再現コード

1 つのソース ファイルまたは前処理済み再現コードに問題をまとめることができず、問題にリンク再現コードが必要ない場合は、IDE プロジェクトを調査できます。 この場合も、適切な再現コードの作成方法に関するすべてのガイダンス (コードは最小限の自己完結型にすること、問題が Microsoft の最新ツールで発生すること、および関連する場合は、問題が他のコンパイラでは確認されていないこと) が適用されます。

最小限の IDE プロジェクトとして再現コードを作成し、ディレクトリ構造全体を .zip ファイルなどに圧縮してパッケージ化した後、レポートに添付します。

## <a name="ways-to-send-your-report"></a>レポートを送信する方法

レポートを提出するには複数の方法があります。 Visual Studio に組み込まれている[問題の報告ツール](/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)、または [Visual Studio Developer Community](https://developercommunity.visualstudio.com/) (Visual Studio 開発者コミュニティ) ページを使用できます。 電子メールでレポートを送信することもできますが、最初の 2 つの方法をお勧めします。 どれを選択するかは、レポートを調査するエンジニアとの連絡方法、および進捗状況を追跡するかどうか、コミュニティとレポートを共有するかどうかによって異なります。

> [!NOTE]
> レポートの送信方法に関係なく、Microsoft はお客様のプライバシーを尊重します。 お客様から送信していただいたデータの扱いについて詳しくは、「[Microsoft Visual Studio 製品ファミリのプライバシーに関する声明](https://www.visualstudio.com/dn948229)」をご覧ください。

### <a name="use-the-report-a-problem-tool"></a>問題の報告ツールを使う

Visual Studio の**問題の報告**ツールを使うと、Visual Studio のユーザーはわずか数クリックでさまざまな問題を報告できます。 IDE を終了することなく、簡単なフォームを使って、発生している問題についての詳細な情報を指定し、レポートを送信できます。

**問題の報告**ツールを通して問題を報告する方法は、IDE からは簡単で便利です。 このツールには、**[サイド リンク バー]** 検索ボックスの横にある **[フィードバックの送信]** アイコンを選択することにより、タイトルバーからアクセスすることができます。あるいは、メニュー バーから、**[ヘルプ]** > **[フィードバックの送信]** > **[問題の報告]** の順に選択してアクセスすることもできます。

問題を報告することにした場合は、まず、開発者コミュニティを調べて同様の問題が発生していないかを確認します。 以前に同様の問題が報告されている場合は、そのトピックに賛成票を投じ、具体例な説明を含めたコメントを追加します。 同様の問題が見つからない場合は、Visual Studio フィードバック ダイアログの下部にある **[新しい問題を報告する]** ボタンを選択して、問題を報告するための手順に従います。

### <a name="use-the-visual-studio-developer-community-pages"></a>Visual Studio 開発者コミュニティ ページを使用する

Visual Studio で問題を報告するためのもう 1 つの便利な方法として Visual Studio 開発者コミュニティ ページがあります。このページでは Visual Studio、C++ コンパイラ、ツール、ライブラリについて解決策を検索できます。 [Visual Studio に関する質問](https://developercommunity.visualstudio.com/spaces/8/index.html)ページは、IDE またはインストールに関する問題を報告する場所です。 C++ コンパイラ、リンカー、およびその他のツールやライブラリでの問題については、[C++ に関する質問](https://developercommunity.visualstudio.com/spaces/62/index.html)ページを使用してください。

開発者コミュニティの各ページの上部付近にあるバナーは検索ボックスであり、自分が遭遇している問題と同様の内容を報告している投稿またはトピックを検索することができます。 遭遇している問題に関連する解決策またはその他の有用な情報が既存のトピックで報告されていることを確認できる場合があります。 他のユーザーが以前に同じ問題を報告している場合は、新たに問題レポートを作成するのではなく、そのトピックに対して賛成票を投じ、コメントを追加してください。

以前に問題が報告されていない場合は、開発者コミュニティ ページの検索ボックスの横にある **[問題の報告]** ボタンを選択します。 Visual Studio アカウントへのサインイン、および開発者コミュニティ アプリがプロファイルにアクセスすることへの同意を求められる場合があります。 サインインすると、問題を報告できるページに直接移動します。 再現コードとコマンド ライン、スクリーン ショット、関連するディスカッションへのリンク、および関連性があり有用だと思われるその他の情報を含めることができます。

### <a name="send-an-email"></a>メールを送信する

メールは、Visual C++ チームにレポートを直接送るもう 1 つの方法です。 アドレスは [ compilercrash@microsoft.com](mailto:compilercrash@microsoft.com) です。電子メールによる方法は他の 2 つの方法を使用できない場合にのみ使用してください。メールの場合は、**問題の報告**ツールや Web ページを使用して開発者コミュニティに報告された問題ほど綿密に追跡されず、コメントおよび解決策が他の Visual Studio ユーザーに表示されないためです。

レポートをメールで送信する場合は、メール メッセージの本文として次のテンプレートを使用できます。 ソース コードなどの情報をメール本文に含めない場合は、忘れずにソース コード ファイルや他のファイルを添付してください。

```Example
To: compilercrash@microsoft.com
Subject: Visual C++ Error Report
-----

Compiler version:

CL.EXE command line:

Problem description:

Source code and repro steps:

```

> [!TIP]
> Visual Studio で発生する可能性がある、ツールセットに関係しない他の種類の問題 (たとえば、UI の問題、IDE の機能の不具合、一般的なクラッシュなど) の場合は、問題の報告ツールを使うのが特に適しています。このツールのスクリーンショット機能や、発生した問題をもたらした UI 操作を記録する機能が役に立ちます。 これらの他の種類のエラーの報告には、compilercrash@microsoft.com へのメール送信は使わないでください。
