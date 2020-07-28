---
title: /guard:ehcont (EH 継続メタデータを有効にする)
description: 'Microsoft C++/guard: ehcont コンパイラオプションのリファレンスガイド。'
ms.date: 06/03/2020
f1_keywords:
- /guard:ehcont
- VC.Project.VCCLCompilerTool.GuardEHContMetadata
helpviewer_keywords:
- /guard:ehcont
- /guard:ehcont compiler option
ms.openlocfilehash: c1b960bf13a6a7b7ff67996c9fa5119075216dae
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87190521"
---
# <a name="guardehcont-enable-eh-continuation-metadata"></a>/guard:ehcont (EH 継続メタデータを有効にする)

コンパイラによる EH 継続 (EHCONT) メタデータの生成を有効にします。

## <a name="syntax"></a>構文

> **`/guard:ehcont`**[**`-`**]

## <a name="remarks"></a>解説

オプションを指定 **`/guard:ehcont`** すると、コンパイラは、バイナリのすべての有効な例外処理継続ターゲットの相対仮想アドレス (RVA) の並べ替えられたリストを生成します。 これは、ランタイムと命令ポインターの検証で使用され `NtContinue` `SetThreadContext` ます。 既定で **`/guard:ehcont`** は、はオフであり、明示的に有効にする必要があります。 このオプションを明示的に無効にするには、を使用し **`/guard:ehcont-`** ます。

この **`/guard:ehcont`** オプションは、Visual Studio 2019 バージョン16.7 以降で使用できます。 この機能は、64ビット OS 上の64ビットプロセスでサポートされています。

[制御フロー強制テクノロジ (中央値)](https://software.intel.com/sites/default/files/managed/4d/2a/control-flow-enforcement-technology-preview.pdf)は、リターン指向プログラミング (ROP) ベースの攻撃から保護する、ハードウェアベースのセキュリティ機能です。 制御フローの整合性を適用するために、すべての呼び出し履歴に対して "シャドウスタック" を保持します。

シャドウスタックを使用して、ROP 攻撃を防ぐことができる場合、攻撃者は他の悪用手法を使用することになります。 使用できる技法の1つは、[コンテキスト](/windows/win32/api/winnt/ns-winnt-context)構造内の命令ポインター値を破損させることです。 この構造体は、、、などのスレッドの実行をリダイレクトするシステム呼び出しに渡され `NtContinue` [`RtlRestoreContext`](/windows/win32/api/winnt/nf-winnt-rtlrestorecontext) [`SetThreadContext`](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadcontext) ます。 `CONTEXT`構造体はメモリに格納されます。 含まれている命令ポインターを破損すると、システム呼び出しによって、攻撃者によって制御されるアドレスに実行が転送される可能性があります。 現在、 `NTContinue` 任意の継続ポイントを使用してを呼び出すことができます。 そのため、シャドウスタックが有効になっているときに命令ポインターを検証することが不可欠です。

`RtlRestoreContext`と `NtContinue` は、構造化例外処理 (SEH) 例外アンワインド中に、ブロックを含むターゲットフレームにアンワインドするために使用され **`__except`** ます。 命令ポインターの検証が **`__except`** 失敗する可能性があるため、ブロックの命令ポインターはシャドウスタック上に存在している必要はありません。 **`/guard:ehcont`** コンパイラスイッチは、"EH 継続テーブル" を生成します。 これには、バイナリ内のすべての有効な例外処理継続ターゲットの RVAs の並べ替え済みリストが含まれます。 `NtContinue`は、最初にユーザーが指定した命令ポインターのシャドウスタックを確認し、命令ポインターが見つからない場合は、命令ポインターを含むバイナリからの EH 継続テーブルのチェックを続行します。 含まれているバイナリがテーブルを使用してコンパイルされていない場合は、レガシバイナリとの互換性のために、の `NtContinue` 続行が許可されます。 EHCONT 継続するデータを持たないレガシバイナリと、EHCONT データを含み、テーブルエントリを含まないバイナリを区別することが重要です。 前者は、バイナリ内のすべてのアドレスを有効な継続ターゲットとして許可します。 後者では、バイナリ内のアドレスを有効な継続ターゲットとして使用することは許可されていません。

オプションは、 **`/guard:ehcont`** バイナリの EH 継続ターゲット RVAs を生成するために、コンパイラとリンカーの両方に渡す必要があります。 1 つの `cl` コマンドを使用してバイナリが作成されている場合、コンパイラはリンカーにオプションを渡します。 コンパイラは、オプションも [**`/guard:cf`**](guard-enable-control-flow-guard.md) リンカーに渡します。 を個別にコンパイルしてリンクする場合、これらのオプションは、コンパイラとリンカーの両方のコマンドで設定する必要があります。

を使用してコンパイルされたコード **`/guard:ehcont`** を、それを使用せずにコンパイルされたライブラリおよびオブジェクトファイルにリンクできます。 リンカーは、次のいずれかのシナリオで致命的なエラーを返します。

- コードセクションには、"ローカルアンワインド" があります。 詳細については、「 [try-Finally ステートメント](../../cpp/try-finally-statement.md#abnormal-termination)での異常終了」を参照してください。

- EH (.xdata) セクションには、コードセクションへのポインターが含まれています。これは SEH 用ではありません。

- ポインターは SEH 用ですが、オブジェクトファイルは、Comdat を生成するために関数レベルのリンク ([/gy](gy-enable-function-level-linking.md)) を使用してコンパイルされませんでした。

このようなシナリオではメタデータを生成できないため、リンカーは致命的なエラーを返します。 つまり、例外をスローすると、実行時にクラッシュが発生する可能性があります。

Comdat で見つかったが、を使用してコンパイルされていない SEH セクション情報の場合、 **`/guard:ehcont`** リンカーは警告**LNK4291**を出力します。 この場合、リンカーはセクションに対して正しいが控えめなメタデータを生成します。 この警告を無視するには、 [/ignore (特定の警告を無視する)](ignore-ignore-specific-warnings.md)を使用します。

リンカーがメタデータを生成できない場合は、次のいずれかのエラーが出力されます。

- **`LNK2046`**`: module contains _local_unwind but was not compiled with /guard:ehcont`

- **`LNK2047`**`: module contains C++ EH or complex EH metadata but was not compiled with /guard:ehcont.`

バイナリに EHCONT データが含まれているかどうかを確認するには、バイナリのロード構成をダンプするときに次の要素を探します。

```cmd
e:\>link /dump /loadconfig CETTest.exe
...
            10417500 Guard Flags
...
                       EH Continuation table present      // EHCONT guard flag present
...
    0000000180018640 Guard EH continuation table
                  37 Guard EH continuation count          // May be 0 if no exception handling is used in the binary. Still counts has having EHCONT data.
...
    Guard EH Continuation Table                           // List of RVAs

          Address
          --------
           0000000180002CF5
           0000000180002F03
           0000000180002F0A
...
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コード生成**] プロパティページを選択します。

1. [ **EH 継続メタデータを有効にする**] プロパティを選択します。

1. ドロップダウンコントロールで、 **[はい] (/ガード: ehcont)** を選択して、EH 継続メタデータを有効にするか、[**いいえ] (/ガード: ehcont)** を選択して無効にします。

## <a name="see-also"></a>関連項目

[/ガード (制御フローガードを有効にする)](guard-enable-control-flow-guard.md)\
[MSVC コンパイラオプション](compiler-options.md)\
[MSVC コンパイラのコマンドライン構文](compiler-command-line-syntax.md)
