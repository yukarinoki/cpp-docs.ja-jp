---
title: x64 でのソフトウェア規約
ms.date: 12/17/2018
helpviewer_keywords:
- x64 coding conventions
- Visual C++, x64 calling conventions
ms.assetid: 750f3d97-1706-4840-b2fc-41a007329a08
ms.openlocfilehash: 11d29b6c31ccecfe5b9c51c2f9311213bd4a6732
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78865601"
---
# <a name="x64-software-conventions"></a>x64 でのソフトウェア規約

このセクションではC++ 、x64 の呼び出し規則の手法について説明します。これは、x86 アーキテクチャの64ビット拡張です。

## <a name="overview-of-x64-calling-conventions"></a>X64 呼び出し規則の概要

X86 と x64 の2つの重要な違いは、64ビットのアドレス指定機能と、一般的な使用のための 16 64 ビットレジスタのフラットセットです。 展開されたレジスタセットの場合、x64 では[__fastcall](../cpp/fastcall.md)の呼び出し規約と、RISC ベースの例外処理モデルを使用します。 `__fastcall` 規約では、最初の4つの引数にレジスタを使用し、スタックフレームを使用して追加の引数を渡します。 レジスタの使用、スタックパラメーター、戻り値、スタックアンワインドなど、x64 呼び出し規則の詳細については、「 [x64 呼び出し規則](x64-calling-convention.md)」を参照してください。

## <a name="enable-optimization-for-x64"></a>X64 の最適化を有効にする

次のコンパイラオプションは、x64 用にアプリケーションを最適化するのに役立ちます。

- [/favor (アーキテクチャ固有の最適化)](../build/reference/favor-optimize-for-architecture-specifics.md)

## <a name="types-and-storage"></a>型とストレージ

このセクションでは、x64 アーキテクチャのデータ型の列挙とストレージについて説明します。

### <a name="scalar-types"></a>スカラー型

どのような配置でもデータにアクセスできますが、パフォーマンスの低下を避けるために、データを自然な境界 (または複数) に配置することをお勧めします。 列挙型は定数整数で、32ビット整数として扱われます。 次の表では、次のアラインメント値を使用したアラインメントに関連するデータの種類の定義と推奨されるストレージについて説明します。

- バイト-8 ビット

- ワード16ビット

- ダブルワード-32 ビット

- Quadword-64 ビット

- Octaword-128 ビット

|||||
|-|-|-|-|
|スカラー型|C データ型|ストレージサイズ (バイト単位)|推奨されるアラインメント|
|**INT8**|**char**|1|Byte|
|**UINT8**|**unsigned char**|1|Byte|
|**INT16**|**short**|2|Word|
|**UINT16**|**unsigned short**|2|Word|
|**INT32**|**int**、 **long**|4|上位|
|**UINT32**|**unsigned int、unsigned long**|4|上位|
|**INT64**|**__int64**|8|Quadword|
|**UINT64**|**unsigned __int64**|8|Quadword|
|**FP32 (単精度)**|**float**|4|上位|
|**FP64 (倍精度)**|**double**|8|Quadword|
|**POINTER**|__\*__|8|Quadword|
|**__m64**|**構造体の __m64**|8|Quadword|
|**__m128**|**構造体の __m128**|16|Octaword|

### <a name="aggregates-and-unions"></a>集計と共用体

配列、構造体、共用体などの他の型には、一貫性のある集計と共用体のストレージとデータの取得を保証する、より厳密なアラインメント要件があります。 配列、構造体、および共用体の定義を次に示します。

- Array

   隣接するデータオブジェクトの順序付けられたグループが含まれています。 各オブジェクトは*要素*と呼ばれます。 配列内のすべての要素のサイズとデータ型は同じです。

- 構造体

   データオブジェクトの順序付けられたグループが含まれています。 配列の要素とは異なり、構造内のデータオブジェクトは、異なるデータ型とサイズを持つことができます。 構造体の各データオブジェクトは、*メンバー*と呼ばれます。

- Union

   名前付きメンバーのセットのいずれかを保持するオブジェクト。 名前付きセットのメンバーは任意の型にすることができます。 共用体に割り当てられたストレージは、その共用体の最大メンバーに必要なストレージと、アラインメントに必要な埋め込みに相当します。

次の表は、共用体と構造体のスカラーメンバーに対して強く推奨される配置を示しています。

||||
|-|-|-|
|スカラー型|C データ型|必須のアラインメント|
|**INT8**|**char**|Byte|
|**UINT8**|**unsigned char**|Byte|
|**INT16**|**short**|Word|
|**UINT16**|**unsigned short**|Word|
|**INT32**|**int**、 **long**|上位|
|**UINT32**|**unsigned int、unsigned long**|上位|
|**INT64**|**__int64**|Quadword|
|**UINT64**|**unsigned __int64**|Quadword|
|**FP32 (単精度)**|**float**|上位|
|**FP64 (倍精度)**|**double**|Quadword|
|**POINTER**|<strong>\*</strong>|Quadword|
|**__m64**|**構造体の __m64**|Quadword|
|**__m128**|**構造体の __m128**|Octaword|

次の集約アラインメント規則が適用されます。

- 配列のアラインメントは、配列の要素のいずれかのアラインメントと同じです。

- 構造体または共用体の先頭の配置は、個々のメンバーの最大配置です。 構造体または共用体内の各メンバーは、前の表で定義されている適切な配置に配置する必要があります。これには、前のメンバーに応じて、暗黙的な内部パディングが必要になる場合があります。

- 構造体のサイズは、そのアラインメントの整数倍数である必要があります。これは、最後のメンバーの後にパディングが必要になる場合があります。 構造体と共用体は配列でグループ化できるため、構造体または共用体の各配列要素は、事前に決定された適切なアラインメントで開始および終了する必要があります。

- 前のルールが保持されている限り、データをアラインメント要件よりも大きくすることができます。

- 個々のコンパイラは、サイズ上の理由で構造体のパッキングを調整する場合があります。 たとえば、 [/zp (構造体メンバーのアラインメント)](../build/reference/zp-struct-member-alignment.md)では、構造体のパッキングを調整できます。

### <a name="examples-of-structure-alignment"></a>構造体の配置例

次の4つの例では、それぞれがアラインされた構造体または共用体を宣言しています。また、対応する数値は、メモリ内の構造体または共用体のレイアウトを示します 図の各列はメモリのバイトを表し、列の数値はそのバイトの移動を示します。 各図の2番目の行の名前は、宣言内の変数の名前に対応しています。 影付きの列は、指定された配置を実現するために必要な埋め込みを示します。

#### <a name="example-1"></a>例 1

```C
// Total size = 2 bytes, alignment = 2 bytes (word).

_declspec(align(2)) struct {
    short a;      // +0; size = 2 bytes
}
```

![AMD 変換例1構造レイアウト](../build/media/vcamd_conv_ex_1_block.png "AMD 変換例1構造レイアウト")

#### <a name="example-2"></a>例 2

```C
// Total size = 24 bytes, alignment = 8 bytes (quadword).

_declspec(align(8)) struct {
    int a;       // +0; size = 4 bytes
    double b;    // +8; size = 8 bytes
    short c;     // +16; size = 2 bytes
}
```

![AMD 変換例2構造レイアウト](../build/media/vcamd_conv_ex_2_block.png "AMD 変換例2構造レイアウト")

#### <a name="example-3"></a>例 3

```C
// Total size = 12 bytes, alignment = 4 bytes (doubleword).

_declspec(align(4)) struct {
    char a;       // +0; size = 1 byte
    short b;      // +2; size = 2 bytes
    char c;       // +4; size = 1 byte
    int d;        // +8; size = 4 bytes
}
```

![AMD 変換例2構造レイアウト](../build/media/vcamd_conv_ex_3_block.png "AMD 変換例2構造レイアウト")

#### <a name="example-4"></a>例 4

```C
// Total size = 8 bytes, alignment = 8 bytes (quadword).

_declspec(align(8)) union {
    char *p;      // +0; size = 8 bytes
    short s;      // +0; size = 2 bytes
    long l;       // +0; size = 4 bytes
}
```

![AMD 変換の例 4 union layouit](../build/media/vcamd_conv_ex_4_block.png "AMD 変換の例 4 union layouit")

### <a name="bitfields"></a>ビット フィールド

構造体のビットフィールドは64ビットに制限されており、符号付き int、unsigned int、int64、または unsigned int64 の型にすることができます。 型の境界を越えるビットフィールドは、ビットをスキップして、ビットフィールドを次の型のアラインメントに揃えます。 たとえば、整数ビットフィールドは32ビット boundry にまたがることはできません。

### <a name="conflicts-with-the-x86-compiler"></a>X86 コンパイラとの競合

4バイトを超えるデータ型は、x86 コンパイラを使用してアプリケーションをコンパイルしたときに、スタックに自動的にアラインされません。 X86 コンパイラのアーキテクチャは4バイトでアラインされたスタックであるため、64ビットの整数のように4バイトを超えるものは、8バイトのアドレスに自動的に配置することはできません。

整列されていないデータの操作には、2つの影響があります。

- 配置された場所にアクセスする場合よりも、アラインメントされていない場所にアクセスするには時間がかかることがあります。

- 整列されていない場所は、インタロック操作では使用できません。

より厳密なアラインメントが必要な場合は、変数宣言で `__declspec(align(N))` を使用します。 これにより、コンパイラは、指定された仕様に合わせてスタックを動的に整列します。 ただし、実行時にスタックを動的に調整すると、アプリケーションの実行速度が低下する可能性があります。

## <a name="register-usage"></a>使用状況の登録

X64 アーキテクチャでは、16個の汎用レジスタ (これは整数レジスタとも呼ばれます) と、浮動小数点使用に使用できる16個の XMM/YMM レジスタが用意されています。 volatile レジスタは、呼び出しで使用された後に内容が破棄されることが、呼び出し元によって想定されているスクラッチ レジスタです。 関数呼び出しで使用された後もレジスタの値を保持するには非 volatile レジスタが必要です。使用された非 volatile レジスタの保存は、呼び出し先が行う必要があります。

### <a name="register-volatility-and-preservation"></a>揮発性と保持の登録

関数呼び出しで各レジスタがどのように使用されるかを次の表に示します。

||||
|-|-|-|
|[登録]|Status|用途|
|RAX|Volatile|戻り値レジスタ|
|RCX|Volatile|1 番目の整数引数|
|RDX|Volatile|2 番目の整数引数|
|R8|Volatile|3 番目の整数引数|
|R9|Volatile|4 番目の整数引数|
|R10:R11|Volatile|必要に応じて、呼び出し元によって保持される必要があります。syscall/sysret 命令で使用されます。|
|R12:R15|非 volatile|呼び出し先によって保持される必要があります。|
|RDI|非 volatile|呼び出し先によって保持される必要があります。|
|RSI|非 volatile|呼び出し先によって保持される必要があります。|
|RBX|非 volatile|呼び出し先によって保持される必要があります。|
|RBP|非 volatile|フレーム ポインターとして使用できます。呼び出し先によって保持される必要があります。|
|RSP|非 volatile|スタック ポインター|
|XMM0, YMM0|Volatile|1 番目の FP 引数。`__vectorcall` が使用された場合の 1 番目のベクター型引数。|
|XMM1, YMM1|Volatile|2 番目の FP 引数。`__vectorcall` が使用された場合の 2 番目のベクター型引数。|
|XMM2, YMM2|Volatile|3 番目の FP 引数。`__vectorcall` が使用された場合の 3 番目のベクター型引数。|
|XMM3, YMM3|Volatile|4 番目の FP 引数。`__vectorcall` が使用された場合の 4 番目のベクター型引数。|
|XMM4, YMM4|Volatile|必要に応じて、呼び出し元によって保持される必要があります。`__vectorcall` が使用された場合の 5 番目のベクター型引数。|
|XMM5, YMM5|Volatile|必要に応じて、呼び出し元によって保持される必要があります。`__vectorcall` が使用された場合の 6 番目のベクター型引数。|
|XMM6:XMM15, YMM6:YMM15|非 volatile (XMM)、volatile (YMM の上半分)|は、呼び出し先によって保持される必要があります。 必要に応じて、呼び出し元によって YMM レジスタが保持される必要があります。|

関数の終了時および C ランタイムライブラリの呼び出しと Windows システムの呼び出しに対する関数の入力時に、CPU フラグレジスタの方向フラグがクリアされることが想定されています。

## <a name="stack-usage"></a>スタックの使用状況

X64 のスタック割り当て、アラインメント、関数型、およびスタックフレームの詳細については、「 [x64 stack usage](stack-usage.md)」を参照してください。

## <a name="prolog-and-epilog"></a>プロローグとエピローグ

スタック領域の割り当て、他の関数の呼び出し、不揮発性レジスタの保存、例外処理の使用などのすべての関数は、それぞれの関数テーブルエントリに関連付けられたアンワインドデータでアドレス制限が記述されたプロローグを持つ必要があります。また、エピローグ at関数が終了するたびに終了します。 X64 で必要なプロローグとエピローグコードの詳細については、「 [x64 プロローグとエピローグ](prolog-and-epilog.md)」を参照してください。

## <a name="x64-exception-handling"></a>x64 での例外処理

構造化例外処理およびC++ x64 での例外処理動作を実装するために使用される規則とデータ構造については、「 [x64 例外処理](exception-handling-x64.md)」を参照してください。

## <a name="intrinsics-and-inline-assembly"></a>組み込みおよびインラインアセンブリ

X64 コンパイラの制約の1つは、インラインアセンブラーをサポートしないことです。 つまり、C またはC++に記述できない関数は、サブルーチンとして記述するか、コンパイラでサポートされている組み込み関数として記述する必要があります。 特定の機能はパフォーマンスに影響しますが、他の関数はそうではありません。 パフォーマンスを重視する関数は、組み込み関数として実装する必要があります。

コンパイラでサポートされている組み込みについては、「[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)」を参照してください。

## <a name="image-format"></a>イメージ形式

X64 実行可能イメージ形式は PE32 + です。 実行可能イメージ (Dll と Exe の両方) は最大サイズが 2 gb に制限されているため、32ビットの変位による相対アドレスを使用して、静的な画像データに対処できます。 このデータには、インポートアドレステーブル、文字列定数、静的グローバルデータなどが含まれます。

## <a name="see-also"></a>参照

[呼び出し規約](../cpp/calling-conventions.md)
