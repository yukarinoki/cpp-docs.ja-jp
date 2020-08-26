---
title: x64 での例外処理
ms.date: 10/14/2019
helpviewer_keywords:
- C++ exception handling, x64
- exception handling, x64
ms.assetid: 41fecd2d-3717-4643-b21c-65dcd2f18c93
ms.openlocfilehash: 3d973354f94ca8c9f2e0901e60f2a8009ac08cd6
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835052"
---
# <a name="x64-exception-handling"></a>x64 での例外処理

x64 での構造化例外処理と C++ 例外処理のコーディング規則と動作の概要。 例外処理の一般的な情報については、「[Visual C++ での例外処理](../cpp/exception-handling-in-visual-cpp.md)」を参照してください。

## <a name="unwind-data-for-exception-handling-debugger-support"></a>例外処理とデバッガー サポートのためのアンワインド データ

例外処理とデバッグのサポートには、いくつかのデータ構造が必要です。

### <a name="struct-runtime_function"></a>構造体 RUNTIME_FUNCTION

テーブルベースの例外処理には、スタック スペースを割り当てるか、別の関数 (たとえば、非リーフ関数) を呼び出すすべての関数に対してテーブル エントリが必要です。 関数テーブルのエントリの形式は次のとおりです。

|サイズ|値|
|-|-|
|ULONG|関数の開始アドレス|
|ULONG|関数の終了アドレス|
|ULONG|アンワインド情報のアドレス|

RUNTIME_FUNCTION 構造体は、メモリ内で DWORD にアラインされている必要があります。 すべてのアドレスはイメージ相対です。つまり、関数テーブル エントリを含むイメージの開始アドレスからの 32 ビット オフセットです。 これらのエントリは並べ替えられ、PE32+ イメージの .pdata セクションに配置されます。 動的に生成される関数 [JIT コンパイラ] の場合、これらの関数をサポートするランタイムでは、RtlInstallFunctionTableCallback または RtlAddFunctionTable を使用して、この情報をオペレーティング システムに提供する必要があります。 そうしないと、例外処理とプロセスのデバッグの信頼性が低下します。

### <a name="struct-unwind_info"></a>構造体 UNWIND_INFO

アンワインド データ情報構造体は、関数がスタック ポインターに及ぼす影響を記録するために使用され、不揮発性レジスタがスタックに保存されます。

|サイズ|値|
|-|-|
|UBYTE:3|バージョン|
|UBYTE:5|フラグ|
|UBYTE|プロローグのサイズ|
|UBYTE|アンワインド コードの数|
|UBYTE:4|フレーム レジスタ|
|UBYTE:4|フレーム レジスタ オフセット (スケールあり)|
|USHORT \* n|アンワインド コード配列|
|変数|以下の形式 (1) または (2) のいずれかを指定できます|

(1) 例外ハンドラー

|サイズ|値|
|-|-|
|ULONG|例外ハンドラーのアドレス|
|変数|言語固有のハンドラー データ (省略可能)|

(2) チェーン アンワインド情報

|サイズ|値|
|-|-|
|ULONG|関数の開始アドレス|
|ULONG|関数の終了アドレス|
|ULONG|アンワインド情報のアドレス|

UNWIND_INFO 構造体は、メモリ内で DWORD にアラインされている必要があります。 各フィールドの意味は次のとおりです。

- **Version**

   アンワインド データのバージョン番号 (現在は 1)。

- **フラグ**

   現在、次の 3 つのフラグが定義されています。

   |フラグ|説明|
   |-|-|
   |`UNW_FLAG_EHANDLER`| この関数には、例外を調べる必要がある関数を探すときに、呼び出す必要がある例外ハンドラーがあります。|
   |`UNW_FLAG_UHANDLER`| この関数には、例外をアンワインドするときに呼び出す必要がある終了ハンドラーがあります。|
   |`UNW_FLAG_CHAININFO`| このアンワインド情報構造体は、プロシージャのプライマリではありません。 そうではなく、チェーン アンワインド情報エントリは、以前の RUNTIME_FUNCTION エントリの内容です。 詳細については、「[チェーン アンワインド情報構造体](#chained-unwind-info-structures)」を参照してください。 このフラグが設定されている場合は、UNW_FLAG_EHANDLER および UNW_FLAG_UHANDLER フラグをクリアする必要があります。 また、フレーム レジスタと固定スタックの割り当てフィールドには、プライマリ アンワインド情報と同じ値が必要です。|

- **プロローグのサイズ**

   関数プロローグの長さ (バイト単位)。

- **アンワインド コードの数**

   アンワインド コード配列内のスロット数。 UWOP_SAVE_NONVOL など、一部のアンワインド コードには、配列に複数のスロットが必要です。

- **フレーム レジスタ**

   ゼロ以外の場合、関数にはフレーム ポインター (FP) を使用します。このフィールドは、UNWIND_CODE ノードの演算情報フィールドに同じエンコードを使用して、フレーム ポインターとして使用される不揮発性レジスタの番号です。

- **フレーム レジスタ オフセット (スケールあり)**

   フレーム レジスタ フィールドがゼロ以外の場合、このフィールドは、確立時に FP レジスタに適用される RSP からのスケールされたオフセットです。 実際の FP レジスタは RSP + 16 \* に設定されます。この数値では、0 から 240 のオフセットが可能です。 このオフセットによって、FP レジスタから動的スタック フレームのローカル スタック割り当ての中央を指すことができるようになるため、より短い命令でより良いコード密度を達成できます (つまり、より多くの命令で、8 ビット符号付きオフセット形式を使用できます)。

- **アンワインド コード配列**

   不揮発性レジスタと RSP に対するプロローグの影響を説明する項目の配列。 個々の項目の意味については、UNWIND_CODE のセクションを参照してください。 アラインメントのために、この配列には常に偶数のエントリがあり、最後のエントリは使用されない可能性があります。 この場合、配列はアンワインド コード フィールドのカウントで示されるよりも 1 つ長くなります。

- **例外ハンドラーのアドレス**

   フラグ UNW_FLAG_CHAININFO がクリアされていて、フラグ UNW_FLAG_EHANDLER または UNW_FLAG_UHANDLER のいずれかが設定されている場合、関数の言語固有の例外または終了ハンドラーへのイメージ相対ポインター。

- **言語固有のハンドラー データ**

   関数の言語固有の例外ハンドラー データ。 このデータの形式は指定されておらず、完全に使用中の特定の例外ハンドラーによって決まります。

- **チェーン アンワインド情報**

   フラグ UNW_FLAG_CHAININFO が設定されている場合、UNWIND_INFO 構造体は 3 つの UWORD で終了します。  これらの UWORD は、チェーン アンワインドの関数に関する RUNTIME_FUNCTION 情報を表します。

### <a name="struct-unwind_code"></a>構造体 UNWIND_CODE

アンワインド コード配列は、不揮発性レジスタと RSP に影響を与える一連の演算をプロローグに記録するために使用されます。 各コード項目の形式は次のとおりです。

|サイズ|値|
|-|-|
|UBYTE|プロローグ内のオフセット|
|UBYTE:4|アンワインド オペコード|
|UBYTE:4|演算情報|

配列は、プロローグ内のオフセットの降順で並べ替えられます。

#### <a name="offset-in-prolog"></a>プロローグ内のオフセット

この演算を実行する命令の終わりの (プロローグの先頭からの) オフセット + 1 (つまり、次の命令の開始のオフセット)。

#### <a name="unwind-operation-code"></a>アンワインド オペコード

メモ:一部のオペコードには、ローカル スタック フレームの値への符号なしオフセットが必要です。 このオフセットは、最初から、つまり固定スタック割り当ての最小アドレスからです。 UNWIND_INFO のフレーム レジスタ フィールドがゼロの場合、これは RSP からのオフセットです。 フレーム レジスタ フィールドがゼロ以外の場合、これは、FP レジスタが確立されたときに RSP が配置されていた場所からのオフセットです。 これは、FP レジスタから FP レジスタ オフセットを引いた値 (16 \* UNWIND_INFO のスケールされたフレーム レジスタ オフセット) と等しくなります。 FP レジスタを使用する場合、オフセットを受け取るアンワインド コードは、FP レジスタがプロローグで確立された後で使用する必要があります。

`UWOP_SAVE_XMM128` と `UWOP_SAVE_XMM128_FAR` を除くすべてのオペコードでは、対象となるすべてのスタック値は 8 バイト境界に格納されるため、オフセットは常に 8 の倍数になります (スタック自体は常に 16 バイト境界でアラインされます)。 短いオフセット (512K 未満) を受け取るオペコードの場合、このコードのノードの最後の USHORT には、オフセットを 8 で割った値が保持されます。 長いオフセット (512K 以上、4 GB 未満のオフセット) を受け取るオペコードの場合、このコードの最後の 2 つの USHORT ノードに (リトルエンディアン形式で) オフセットが保持されます。

オペコード `UWOP_SAVE_XMM128` および `UWOP_SAVE_XMM128_FAR` の場合、オフセットは常に 16 の倍数です。これは、すべての 128 ビット XMM 演算は 16 バイト境界でアラインされたメモリで発生する必要があるためです。 そのため、`UWOP_SAVE_XMM128` には 16 の倍率が使用され、1M 未満のオフセットが許可されます。

アンワインド オペコードは、次のいずれかの値になります。

- `UWOP_PUSH_NONVOL` (0) 1 ノード

  不揮発性整数レジスターをプッシュし、RSP を 8 ずつデクリメントします。 演算情報はレジスタの番号です。 エピローグに制約があるため、`UWOP_PUSH_NONVOL` アンワインド コードはプロローグの最初に出現し、それに対応してアンワインド コード配列の最後に出現する必要があります。 この相対的な順序は、`UWOP_PUSH_MACHFRAME` を除く他のすべてのアンワインド コードに適用されます。

- `UWOP_ALLOC_LARGE` (1) 2 または 3 ノード

  スタックに大きな領域を割り当てます。 2 つの形式があります。 演算情報が 0 の場合、割り当てのサイズを 8 で割ったものが次のスロットに記録され、最大 512K - 8 の割り当てが可能になります。 演算情報が 1 の場合、割り当てのスケールなしのサイズが次の 2 つのスロットにリトルエンディアン形式で記録され、最大 4GB - 8 の割り当てが可能になります。

- `UWOP_ALLOC_SMALL` (2) 1 ノード

  小さいサイズの領域をスタックに割り当てます。 割り当てのサイズは演算情報フィールド \* 8 + 8 であり、8 から 128 バイトの割り当てが可能です。

  スタック割り当てのアンワインド コードには、可能な限り短いエンコードを常に使用するようにします。

  |**アロケーション サイズ**|**アンワインド コード**|
  |-|-|
  |8 から 128 バイト|`UWOP_ALLOC_SMALL`|
  |136 から 512K - 8 バイト|`UWOP_ALLOC_LARGE`、演算情報 = 0|
  |512K から 4G - 8 バイト|`UWOP_ALLOC_LARGE`、演算情報 = 1|

- `UWOP_SET_FPREG` (3) 1 ノード

  現在の RSP のオフセットにレジスタを設定して、フレーム ポインター レジスタを確立します。 オフセットは、UNWIND_INFO \* 16 のフレーム レジスタ オフセット (スケールあり) フィールドと等しく、0 から 240 のオフセットが可能です。 オフセットを使用すると、固定スタック割り当ての中央を指すフレーム ポインターを確立できます。その結果、より多くのアクセスで短い命令形式を使用できるようになるので、コードの密度が向上します。 演算情報フィールドは予約されているため、使用しないでください。

- `UWOP_SAVE_NONVOL` (4) 2 ノード

  PUSH ではなく MOV を使用して、不揮発性整数レジスターをスタックに保存します。 このコードは主に "*shrink-wrapping (シュリンクラッピング)* " のために使用され、不揮発性レジスタは以前に割り当てられた位置のスタックに保存されます。 演算情報はレジスタの番号です。 8 の倍率でスケールされたスタック オフセットは、前述の注記で説明したように、次のアンワインド オペコード スロットに記録されます。

- `UWOP_SAVE_NONVOL_FAR` (5) 3 ノード

  PUSH ではなく MOV を使用して、長いオフセットのスタックに不揮発性整数レジスタを保存します。 このコードは主に "*shrink-wrapping (シュリンクラッピング)* " のために使用され、不揮発性レジスタは以前に割り当てられた位置のスタックに保存されます。 演算情報はレジスタの番号です。 スケールなしのスタック オフセットは、前述の注記で説明したように、次の 2 つのアンワインド オペコード スロットに記録されます。

- `UWOP_SAVE_XMM128` (8) 2 ノード

  不揮発性 XMM レジスタの 128 ビットすべてをスタックに保存します。 演算情報はレジスタの番号です。 16 の倍率でスケールされたスタック オフセットは、次のスロットに記録されます。

- `UWOP_SAVE_XMM128_FAR` (9) 3 ノード

  長いオフセットを使用して、不揮発性 XMM レジスタの 128 ビットすべてをスタックに保存します。 演算情報はレジスタの番号です。 スケールなしのスタック オフセットは、次の 2 つのスロットに記録されます。

- `UWOP_PUSH_MACHFRAME` (10) 1 ノード

  マシン フレームをプッシュします。  このアンワインド コードは、ハードウェアの割り込みまたは例外の影響を記録するために使用されます。 2 つの形式があります。 演算情報が 0 の場合、次いずれかのフレームがスタックにプッシュされています。

  |場所|値|
  |-|-|
  |RSP+32|SS|
  |RSP+24|以前の RSP|
  |RSP+16|EFLAGS|
  |RSP+8|CS|
  |RSP|RIP|

  演算情報が 1 の場合は、次のいずれかのフレームがプッシュされています。

  |場所|値|
  |-|-|
  |RSP+40|SS|
  |RSP+32|以前の RSP|
  |RSP+24|EFLAGS|
  |RSP+16|CS|
  |RSP+8|RIP|
  |RSP|エラー コード|

  このアンワインド コードは常にダミーのプロローグに出現します。実際には実行されませんが、割り込みルーチンの実際のエントリ ポイントの前に出現します。マシン フレームのプッシュをシミュレートする場所を用意するためにのみ存在します。 `UWOP_PUSH_MACHFRAME` によってそのシミュレーションが記録されます。これは、マシンによって概念的に次の演算が実行されたことを示します。

  1. スタックの先頭から *Temp* に RIP 戻り先アドレスをポップします
  
  1. SS をプッシュします

  1. 以前の RSP をプッシュします

  1. EFLAGS をプッシュします

  1. CS をプッシュします

  1. *Temp* をプッシュします

  1. エラー コードをプッシュします (演算情報が 1 の場合)

  シミュレートされた `UWOP_PUSH_MACHFRAME` 演算によって、RSP が 40 (演算情報が 0 の場合) または 48 (演算情報が 1 の場合) ずつデクリメントされます。

#### <a name="operation-info"></a>演算情報

演算情報ビットの意味は、オペコードによって異なります。 汎用 (整数) レジスタをエンコードするには、次のマッピングを使用します。

|ビット|登録|
|-|-|
|0|RAX|
|1|RCX|
|2|RDX|
|3|RBX|
|4|RSP|
|5|RBP|
|6|RSI|
|7|RDI|
|8 から 15|R8 から R15|

### <a name="chained-unwind-info-structures"></a>チェーン アンワインド情報構造体

UNW_FLAG_CHAININFO フラグが設定されている場合、アンワインド情報構造体はセカンダリであり、共有例外ハンドラーおよびチェーン情報アドレス フィールドにはプライマリ アンワインド情報が含まれます。 このサンプル コードでは、`unwindInfo` が UNW_FLAG_CHAININFO フラグが設定されている構造体であると想定して、プライマリ アンワインド情報を取得しています。

```cpp
PRUNTIME_FUNCTION primaryUwindInfo = (PRUNTIME_FUNCTION)&(unwindInfo->UnwindCode[( unwindInfo->CountOfCodes + 1 ) & ~1]);
```

チェーン情報は 2 つの状況で役立ちます。 まず、連続していないコード セグメントに使用できます。 チェーン情報を使用することで、必要なアンワインド情報のサイズを減らすことができます。これは、プライマリ アンワインド情報からアンワインド コード配列を複製する必要がないためです。

また、チェーン情報を使用して、揮発性レジスタの保存をグループ化することもできます。 コンパイラによって、関数エントリのプロローグに含まれなくなるまで、一部の揮発性レジスタの保存が遅延される場合があります。 これらを記録するには、グループ化されたコードの前の関数部分にプライマリ アンワインド情報を配置し、ゼロ以外のサイズのプロローグを使用してチェーン情報を設定します。このチェーン情報のアンワインド コードには、不揮発性レジスタの保存が反映されます。 その場合、アンワインド コードはすべて UWOP_SAVE_NONVOL のインスタンスです。 PUSH を使用して不揮発性レジスタを保存するグループ化や、追加の固定スタック割り当てを使用して RSP レジスタを変更するグループ化はサポートされていません。

UNW_FLAG_CHAININFO が設定されている UNWIND_INFO 項目には、RUNTIME_FUNCTION エントリを含めることができます。この UNWIND_INFO 項目には UNW_FLAG_CHAININFO も設定され、"*multiple shrink-wrapping (マルチ シュリンクラッピング)* " とも呼ばれます。 最終的に、チェーン アンワインド情報ポインターは、UNW_FLAG_CHAININFO がクリアされた UNWIND_INFO 項目に到達します。 この項目は、実際のプロシージャ エントリ ポイントを指すプライマリ UNWIND_INFO 項目です。

## <a name="unwind-procedure"></a>アンワインド プロシージャ

アンワインド コード配列は降順に並べ替えられています。 例外が発生すると、オペレーティング システムによって完全なコンテキストがコンテキスト レコードに格納されます。 次に、例外ディスパッチ ロジックが呼び出され、例外ハンドラーを見つけるためにこれらの手順が繰り返し実行されます。

1. コンテキスト レコードに格納されている現在の RIP を使用して、現在の関数 (またはチェーン UNWIND_INFO エントリの場合は関数部分) が記述された RUNTIME_FUNCTION テーブル エントリを検索します。

1. 関数テーブル エントリが見つからない場合は、リーフ関数内にあるため、RSP では戻りポインターのアドレスを直接指定します。 [RSP] の戻りポインターは更新されたコンテキストに格納され、シミュレートされた RSP は 8 ずつインクリメントされ、手順 1 が繰り返されます。

1. 関数テーブル エントリが見つかった場合、a) エピローグ内、b) プロローグ内、または c) 例外ハンドラーによって処理される可能性のあるコード内という 3 つの領域内に RIP が存在する可能性があります。

   - ケース a) RIP がエピローグ内にある場合、制御は関数を離れ、この関数のこの例外に関連付けられた例外ハンドラーは存在しなくなる可能性があります。呼び出し元の関数のコンテキストを計算するには、エピローグの影響を継続させる必要があります。 RIP がエピローグ内にあるかどうかを判断するには、RIP 以降のコード ストリームを調べます。 そのコード ストリームを正当なエピローグの最後の部分と照合できる場合は、エピローグ内にあるため、エピローグの残りの部分がシミュレートされ、各命令が処理されるときにコンテキスト レコードが更新されます。 この処理の後、手順 1 が繰り返されます。

   - ケース b) RIP がプロローグ内にある場合、コントロールは関数に入っていないため、この関数のこの例外に関連付けられた例外ハンドラーは存在しない可能性があります。呼び出し元関数のコンテキストを計算するには、プロローグの影響を元に戻す必要があります。 関数の開始から RIP までの距離が、アンワインド情報でエンコードされたプロローグ サイズ以下の場合、RIP はプロローグ内にあります。 このプロローグの効果をアンワインドするには、関数の開始からの RIP のオフセット以下のオフセットを持つ最初のエントリのアンワインド コード配列を前方にスキャンし、アンワインド コード配列の残りのすべての項目の効果を元に戻します。 次に、手順 1 を繰り返します。

   - ケース c) RIP がプロローグまたはエピローグ内に存在せず、関数に例外ハンドラーがある (UNW_FLAG_EHANDLER が設定されている) 場合、言語固有のハンドラーが呼び出されます。 ハンドラーによってそのデータがスキャンされ、必要に応じてフィルター関数が呼び出されます。 言語固有のハンドラーから、例外が処理されたこと、または検索が続行されることが返される可能性があります。 また、アンワインドが直接開始される可能性があります。

1. 言語固有のハンドラーから処理済み状態が返された場合、実行は元のコンテキスト レコードを使用して続行されます。

1. 言語固有のハンドラーがない場合、またはハンドラーから "検索の続行" 状態が返された場合は、コンテキスト レコードを呼び出し元の状態にアンワインドする必要があります。 これを行うには、すべてのアンワインド コード配列要素を処理し、それぞれの効果を元に戻します。 次に、手順 1 を繰り返します。

チェーン アンワインド情報が関係する場合でも、これらの基本的な手順に従います。 唯一の違いは、アンワインド コード配列をウォークしてプロローグの効果をアンワインドするときに、配列の最後に到達すると、親のアンワインド情報にリンクされ、そこで見つかったアンワインド コード配列全体がウォークされることです。 このリンクは UNW_CHAINED_INFO フラグのないアンワインド情報に到達するまで続行され、アンワインド コード配列のウォークが完了します。

アンワインド データの最小セットは 8 バイトです。 これは、128 バイト以下のスタックのみを割り当て、おそらく 1 つの不揮発性レジスタが節約された関数を表します。 これは、アンワインド コードのない長さゼロのプロローグのチェーン アンワインド情報構造体のサイズでもあります。

## <a name="language-specific-handler"></a>言語固有のハンドラー

フラグ UNW_FLAG_EHANDLER または UNW_FLAG_UHANDLER が設定されている場合、言語固有のハンドラーの相対アドレスは常に UNWIND_INFO に存在します。 前のセクションで説明したように、言語固有のハンドラーは、例外ハンドラーの検索の一部として、またはアンワインドの一部として呼び出されます。 このプロトタイプは次のようになります。

```cpp
typedef EXCEPTION_DISPOSITION (*PEXCEPTION_ROUTINE) (
    IN PEXCEPTION_RECORD ExceptionRecord,
    IN ULONG64 EstablisherFrame,
    IN OUT PCONTEXT ContextRecord,
    IN OUT PDISPATCHER_CONTEXT DispatcherContext
);
```

**ExceptionRecord** では、標準の Win64 定義を持つ例外レコードへのポインターが提供されます。

**EstablisherFrame** は、この関数の固定スタック割り当てのベースのアドレスです。

**ContextRecord** は、例外が発生したときの例外コンテキスト (例外ハンドラーの場合) または現在の "アンワインド" コンテキスト (終了ハンドラーの場合) を指します。

**DispatcherContext** は、この関数のディスパッチャー コンテキストを指します。 この定義は次のとおりです。

```cpp
typedef struct _DISPATCHER_CONTEXT {
    ULONG64 ControlPc;
    ULONG64 ImageBase;
    PRUNTIME_FUNCTION FunctionEntry;
    ULONG64 EstablisherFrame;
    ULONG64 TargetIp;
    PCONTEXT ContextRecord;
    PEXCEPTION_ROUTINE LanguageHandler;
    PVOID HandlerData;
} DISPATCHER_CONTEXT, *PDISPATCHER_CONTEXT;
```

**ControlPc** は、この関数内の RIP の値です。 この値は、例外アドレスか、制御が確立元の関数から離れたアドレスです。 RIP は、制御がこの関数内の保護されたコンストラクト内にあるかどうかを判断するために使用されます。たとえば、`__try`/ **`__except`** または `__try`/ **`__finally`** の `__try` ブロックなどです。

**ImageBase** は、この関数を含むモジュールのイメージ ベース (読み込みアドレス) であり、関数エントリで使用される 32 ビット オフセットと、相対アドレスを記録するアンワインド情報に追加されます。

**FunctionEntry** では、関数と、その関数のアンワインド情報のイメージベースの相対アドレスを保持する RUNTIME_FUNCTION 関数エントリのポインターが提供されます。

**EstablisherFrame** は、この関数の固定スタック割り当てのベースのアドレスです。

**TargetIp** では、アンワインドの継続アドレスを指定する省略可能な命令アドレスが提供されます。 **EstablisherFrame** が指定されていない場合、このアドレスは無視されます。

**ContextRecord** は、システム例外のディスパッチまたはアンワインド コードで使用される例外コンテキストを指します。

**LanguageHandler** は、呼び出される言語固有の言語ハンドラー ルーチンを指します。

**HandlerData** は、この関数の言語固有のハンドラー データを指します。

## <a name="unwind-helpers-for-masm"></a>MASM のアンワインド ヘルパー

適切なアセンブリ ルーチンを作成するために、一連の疑似演算があります。これは、適切な .pdata と .xdata を作成する実際のアセンブリ命令と並行して使用できます。 また、最も一般的に使用される疑似演算を簡単に使用できるようになる一連のマクロがあります。

### <a name="raw-pseudo-operations"></a>生の擬似演算

|擬似演算|説明|
|-|-|
|PROC FRAME \[:*ehandler*]|関数の構造化例外処理のアンワインド動作に対して、MASM から .pdata に関数テーブル エントリが生成され、.xdata にアンワインド情報が生成されます。  *ehandler* が存在する場合、このプロシージャは言語固有のハンドラーとして .xdata に入力されます。<br /><br /> FRAME 属性を使用する場合、その後に .ENDPROLOG ディレクティブを続ける必要があります。  関数がリーフ関数 (「[関数の種類](../build/stack-usage.md#function-types)」の定義を参照してください) である場合、これらの疑似演算の残りの部分と同様に、FRAME 属性は不要です。|
|.PUSHREG *レジスタ*|プロローグ内の現在のオフセットを使用して、指定されたレジスタ番号の UWOP_PUSH_NONVOL アンワインド コード エントリを生成します。<br /><br /> 不揮発性整数レジスタでのみ使用します。  揮発性レジスタのプッシュには、代わりに .ALLOCSTACK 8 を使用します|
|.SETFRAME *register*, *offset*|指定されたレジスタとオフセットを使用して、フレーム レジスタ フィールドとオフセットをアンワインド情報に入力します。 オフセットは、240 以下の 16 の倍数にする必要があります。 このディレクティブを指定すると、現在のプロローグ オフセットが使用され、指定されたレジスタの UWOP_SET_FPREG アンワインド コード エントリも生成されます。|
|.ALLOCSTACK *size*|プロローグ内の現在のオフセットに指定されたサイズを使用して、UWOP_ALLOC_SMALL または UWOP_ALLOC_LARGE を生成します。<br /><br /> *size* オペランドは 8 の倍数にする必要があります。|
|.SAVEREG *register*, *offset*|指定されたレジスタと、現在のプロローグ オフセットを使用するオフセットに対して UWOP_SAVE_NONVOL または UWOP_SAVE_NONVOL_FAR アンワインド コード エントリを生成します。 MASM によって最も効率的なエンコードが選択されます。<br /><br /> *offset* は正の 8 の倍数にする必要があります。 *offset* は、プロシージャのフレームのベース (通常は RSP 内にあります)、またはフレーム ポインターを使用している場合はスケールなしのフレーム ポインターを基準としています。|
|.SAVEXMM128 *register*, *offset*|指定された XMM レジスタと、現在のプロローグオフセットを使用するオフセットに対して、UWOP_SAVE_XMM128 または UWOP_SAVE_XMM128_FAR アンワインド コード エントリを生成します。 MASM によって最も効率的なエンコードが選択されます。<br /><br /> *offset* は正の 16 の倍数にする必要があります。  *offset* は、プロシージャのフレームのベース (通常は RSP 内にあります)、またはフレーム ポインターを使用している場合はスケールなしのフレーム ポインターを基準としています。|
|.PUSHFRAME \[*code*]|UWOP_PUSH_MACHFRAME アンワインド コード エントリを生成します。 省略可能な *code* が指定されている場合、アンワインド コード エントリには修飾子 1 が与えられます。 それ以外の場合、修飾子は 0 です。|
|.ENDPROLOG|プロローグ宣言の終了を通知します。  関数の最初の 255 バイトで発生する必要があります。|

ほとんどのオペコードを適切に使用したサンプルの関数プロローグを次に示します。

```MASM
sample PROC FRAME
    db      048h; emit a REX prefix, to enable hot-patching
    push rbp
    .pushreg rbp
    sub rsp, 040h
    .allocstack 040h
    lea rbp, [rsp+020h]
    .setframe rbp, 020h
    movdqa [rbp], xmm7
    .savexmm128 xmm7, 020h ;the offset is from the base of the frame
                           ;not the scaled offset of the frame
    mov [rbp+018h], rsi
    .savereg rsi, 038h
    mov [rsp+010h], rdi
    .savereg rdi, 010h ; you can still use RSP as the base of the frame
                       ; or any other register you choose
    .endprolog

; you can modify the stack pointer outside of the prologue (similar to alloca)
; because we have a frame pointer.
; if we didn't have a frame pointer, this would be illegal
; if we didn't make this modification,
; there would be no need for a frame pointer

    sub rsp, 060h

; we can unwind from the next AV because of the frame pointer

    mov rax, 0
    mov rax, [rax] ; AV!

; restore the registers that weren't saved with a push
; this isn't part of the official epilog, as described in section 2.5

    movdqa xmm7, [rbp]
    mov rsi, [rbp+018h]
    mov rdi, [rbp-010h]

; Here's the official epilog

    lea rsp, [rbp+020h] ; deallocate both fixed and dynamic portions of the frame
    pop rbp
    ret
sample ENDP
```

エピローグの例の詳細については、「[x64 でのプロローグとエピローグ](prolog-and-epilog.md)」の「[エピローグ コード](prolog-and-epilog.md#epilog-code)」を参照してください。

### <a name="masm-macros"></a>MASM マクロ

[生の疑似演算](#raw-pseudo-operations)の使用を簡略化するために、ksamd64.inc で定義された一連のマクロが用意されています。これを使用して一般的なプロシージャ プロローグとエピローグを作成できます。

|マクロ|説明|
|-|-|
|alloc_stack(n)|(`sub rsp, n` を使用して) n バイトのスタック フレームを割り当て、適切なアンワインド情報 (.allocstack n) を出力します|
|save_reg *reg*, *loc*|不揮発性レジスタ *reg* を RSP オフセット *loc* のスタックに保存し、適切なアンワインド情報を出力します。 (.savereg reg, loc)|
|push_reg *reg*|不揮発性レジスタ *reg* をスタックにプッシュし、適切なアンワインド情報を出力します。 (.pushreg reg)|
|rex_push_reg *reg*|2 バイトのプッシュを使用して不揮発性レジスタをスタックに保存し、適切なアンワインド情報 (.pushreg reg) を発行します。  プッシュがその関数の最初の命令である場合は、このマクロを使用して、関数のホットパッチが可能であることを確認します。|
|save_xmm128 *reg*, *loc*|不揮発性 XMM レジスタ *reg* を RSP オフセット *loc* のスタックに保存し、適切なアンワインド情報 (.savexmm128 reg、loc) を出力します|
|set_frame *reg*, *offset*|(`mov` または `lea` を使用して) フレーム レジスタ *reg* を RSP + *offset* に設定し、適切なアンワインド情報 (.set_frame reg、offset) を出力します|
|push_eflags|`pushfq` 命令を使用して eflag をプッシュし、適切なアンワインド情報 (.alloc_stack 8) を出力します|

マクロを適切に使用したサンプルの関数プロローグを次に示します。

```MASM
sampleFrame struct
    Fill     dq ?; fill to 8 mod 16
    SavedRdi dq ?; Saved Register RDI
    SavedRsi dq ?; Saved Register RSI
sampleFrame ends

sample2 PROC FRAME
    alloc_stack(sizeof sampleFrame)
    save_reg rdi, sampleFrame.SavedRdi
    save_reg rsi, sampleFrame.SavedRsi
    .end_prolog

; function body

    mov rsi, sampleFrame.SavedRsi[rsp]
    mov rdi, sampleFrame.SavedRdi[rsp]

; Here's the official epilog

    add rsp, (sizeof sampleFrame)
    ret
sample2 ENDP
```

## <a name="unwind-data-definitions-in-c"></a>C でのアンワインド データの定義

アンワインド データの C の記述を次に示します。

```C
typedef enum _UNWIND_OP_CODES {
    UWOP_PUSH_NONVOL = 0, /* info == register number */
    UWOP_ALLOC_LARGE,     /* no info, alloc size in next 2 slots */
    UWOP_ALLOC_SMALL,     /* info == size of allocation / 8 - 1 */
    UWOP_SET_FPREG,       /* no info, FP = RSP + UNWIND_INFO.FPRegOffset*16 */
    UWOP_SAVE_NONVOL,     /* info == register number, offset in next slot */
    UWOP_SAVE_NONVOL_FAR, /* info == register number, offset in next 2 slots */
    UWOP_SAVE_XMM128 = 8, /* info == XMM reg number, offset in next slot */
    UWOP_SAVE_XMM128_FAR, /* info == XMM reg number, offset in next 2 slots */
    UWOP_PUSH_MACHFRAME   /* info == 0: no error-code, 1: error-code */
} UNWIND_CODE_OPS;

typedef union _UNWIND_CODE {
    struct {
        UBYTE CodeOffset;
        UBYTE UnwindOp : 4;
        UBYTE OpInfo   : 4;
    };
    USHORT FrameOffset;
} UNWIND_CODE, *PUNWIND_CODE;

#define UNW_FLAG_EHANDLER  0x01
#define UNW_FLAG_UHANDLER  0x02
#define UNW_FLAG_CHAININFO 0x04

typedef struct _UNWIND_INFO {
    UBYTE Version       : 3;
    UBYTE Flags         : 5;
    UBYTE SizeOfProlog;
    UBYTE CountOfCodes;
    UBYTE FrameRegister : 4;
    UBYTE FrameOffset   : 4;
    UNWIND_CODE UnwindCode[1];
/*  UNWIND_CODE MoreUnwindCode[((CountOfCodes + 1) & ~1) - 1];
*   union {
*       OPTIONAL ULONG ExceptionHandler;
*       OPTIONAL ULONG FunctionEntry;
*   };
*   OPTIONAL ULONG ExceptionData[]; */
} UNWIND_INFO, *PUNWIND_INFO;

typedef struct _RUNTIME_FUNCTION {
    ULONG BeginAddress;
    ULONG EndAddress;
    ULONG UnwindData;
} RUNTIME_FUNCTION, *PRUNTIME_FUNCTION;

#define GetUnwindCodeEntry(info, index) \
    ((info)->UnwindCode[index])

#define GetLanguageSpecificDataPtr(info) \
    ((PVOID)&GetUnwindCodeEntry((info),((info)->CountOfCodes + 1) & ~1))

#define GetExceptionHandler(base, info) \
    ((PEXCEPTION_HANDLER)((base) + *(PULONG)GetLanguageSpecificDataPtr(info)))

#define GetChainedFunctionEntry(base, info) \
    ((PRUNTIME_FUNCTION)((base) + *(PULONG)GetLanguageSpecificDataPtr(info)))

#define GetExceptionDataPtr(info) \
    ((PVOID)((PULONG)GetLanguageSpecificData(info) + 1)
```

## <a name="see-also"></a>関連項目

[x64 ソフトウェア規約](../build/x64-software-conventions.md)
