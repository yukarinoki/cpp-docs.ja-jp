---
description: 詳細については、「予測実行側チャネルの C++ 開発者ガイド」を参照してください。
title: 予測実行側チャネルの C++ 開発者ガイド
ms.date: 07/10/2018
helpviewer_keywords:
- Visual C++, security
- security [C++]
- security [C++], best practices
- Spectre
- CVE-2017-5753
- Speculative Execution
ms.openlocfilehash: 41376f02c04a9baf83fec19791d77c169c73fa31
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320080"
---
# <a name="c-developer-guidance-for-speculative-execution-side-channels"></a>予測実行側チャネルの C++ 開発者ガイド

この記事には、C++ ソフトウェアの予測実行側チャネルハードウェアの脆弱性を特定し、軽減するための開発者向けのガイダンスが含まれています。 これらの脆弱性によって、信頼境界を越えて機密情報が開示される可能性があります。また、命令の予測された順序どおりの実行をサポートするプロセッサで実行されるソフトウェアに影響を与える可能性があります。 この脆弱性のクラスは、最初に2018年1月、で説明されており、その他の背景とガイダンスについては、 [Microsoft のセキュリティアドバイザリ](https://portal.msrc.microsoft.com/security-guidance/advisory/ADV180002)を参照してください。

この記事で説明するガイダンスは、によって表される脆弱性のクラスに関連しています。

1. CVE-2017-5753。 Spectre variant 1 とも呼ばれます。 このハードウェア脆弱性クラスは、条件分岐 misprediction の結果として発生する予測実行によって発生する可能性がある、サイドチャネルに関連しています。 Visual Studio 2017 の Microsoft C++ コンパイラ (バージョン15.5.5 以降) には、 `/Qspectre` CVE-2017-5753 に関連する可能性のある脆弱なコーディングパターンの限られたセットに対するコンパイル時の軽減策を提供するスイッチのサポートが含まれています。 この `/Qspectre` スイッチは、Visual Studio 2015 Update 3 ~ [KB 4338871](https://support.microsoft.com/help/4338871)でも使用できます。 フラグのドキュメントでは、 [`/Qspectre`](../build/reference/qspectre.md) その効果と使用方法について詳しく説明しています。

2. CVE-2018-3639。予測 [ストアバイパス (SSB)](https://aka.ms/sescsrdssb)とも呼ばれます。 このハードウェア脆弱性クラスは、メモリアクセス misprediction の結果として依存ストアの事前の負荷の予測実行によって発生する可能性がある、サイドチャネルに関連しています。

予測実行側チャネルの脆弱性に対するアクセス可能な概要については、これらの問題を検出した調査チームのいずれかによって [Spectre と Meltdown](https://www.youtube.com/watch?v=_4O0zMW-Zu4) が発生した場合のプレゼンテーションに記載されています。

## <a name="what-are-speculative-execution-side-channel-hardware-vulnerabilities"></a>予測実行側チャネルのハードウェアの脆弱性とは何ですか。

最新の Cpu は、命令の予測的な実行と順序を指定しない実行を使用することにより、より高いパフォーマンスを提供します。 たとえば、多くの場合、これは分岐のターゲット (条件と間接) を予測することによって達成されます。これにより、CPU が予測された分岐ターゲットで命令の実行を開始し、実際の分岐ターゲットが解決されるまで、失速を回避できます。 CPU が後で misprediction が発生したことを検出した場合、計算された投機的のコンピューターの状態はすべて破棄されます。 これにより、リタイアメント時の推測に構造的に見える影響はありません。

予測実行は構造的に見える状態には影響しませんが、CPU によって使用されるさまざまなキャッシュなど、非アーキテクチャの状態で残留トレースを残すことができます。 これは、予測実行の残りのトレースであり、これにより、側チャネルの脆弱性が上昇します。 これについて理解を深めるために、次のコードについて考えてみます。これは、CVE-2017-5753 (境界チェックのバイパス) の例を示しています。

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ReadByte(unsigned char *buffer, unsigned int buffer_size, unsigned int untrusted_index) {
    if (untrusted_index < buffer_size) {
        unsigned char value = buffer[untrusted_index];
        return shared_buffer[value * 4096];
    }
}
```

この例では、にバッファー `ReadByte` 、バッファーサイズ、およびインデックスが指定されています。 によって指定された index パラメーター `untrusted_index` は、管理以外のプロセスなど、より低い特権のコンテキストによって提供されます。 `untrusted_index`がより小さい場合は `buffer_size` 、そのインデックス位置にある文字が読み取られ、に `buffer` よって参照されるメモリの共有領域へのインデックス作成に使用され `shared_buffer` ます。

アーキテクチャの観点からは、このコードシーケンスは `untrusted_index` 常により小さくなることが保証されているため、完全に安全です `buffer_size` 。 ただし、予測実行の存在では、が以上の場合でも、CPU が条件分岐を予測ミス割合し、if ステートメントの本体を実行する可能性があり `untrusted_index` `buffer_size` ます。 その結果、CPU は、の境界を超えて (シークレットである可能性がある) バイトを読み取ることができなくなり、その `buffer` バイト値を使用して、を通じて後続の負荷のアドレスを計算することができ `shared_buffer` ます。

CPU はこの misprediction を最終的に検出しますが、CPU キャッシュに残留副作用が残っている可能性があります。これは、から読み取られたバイト値に関する情報を公開 `buffer` します。 これらの副作用は、の各キャッシュラインがアクセスされる速度を調べることによって、システムで実行されている特権の低いコンテキストによって検出でき `shared_buffer` ます。 これを実現するために実行できる手順は次のとおりです。

1. **`ReadByte` を `untrusted_index` より `buffer_size` 小さい値にして、を複数回呼び出し** ます。 攻撃コンテキストによって、対象となるコンテキストが (RPC 経由などで) を呼び出すことがあり `ReadByte` ます。これにより、分岐予測は、 `untrusted_index` よりも小さいと見なされるようにトレーニングされます。 `buffer_size`

2. **のすべてのキャッシュ行 `shared_buffer` をフラッシュ** します。 攻撃コンテキストは、によって参照されるメモリの共有領域にあるすべてのキャッシュ行をフラッシュする必要があり `shared_buffer` ます。 メモリ領域は共有されているため、これは簡単であり、などの組み込みを使用して実現でき `_mm_clflush` ます。

3. **`ReadByte` を `untrusted_index` 超える `buffer_size` を呼び出し** ます。 攻撃コンテキストによって、対象となるコンテキストが呼び出され、 `ReadByte` 分岐が取得されないことが誤って予測されます。 これにより、プロセッサは投機的を超える if ブロックの本体を実行する `untrusted_index` `buffer_size` ため、の範囲外の読み取りが発生し `buffer` ます。 その結果、に `shared_buffer` は、範囲外で読み取られた可能性のあるシークレット値を使用してインデックスが作成されるため、それぞれのキャッシュ行が CPU によって読み込まれます。

4. **で各キャッシュ行を読み取っ `shared_buffer` て、最も高速にアクセスできることを確認** します。 攻撃コンテキストでは、の各キャッシュ行を読み取り、 `shared_buffer` 他よりも大幅に高速に読み込まれるキャッシュラインを検出できます。 これは、手順 3. で発生する可能性のあるキャッシュラインです。 この例では、バイト値とキャッシュ行の間に1:1 のリレーションシップがあるため、攻撃者は、読み取った範囲外のバイトの実際の値を推測できます。

上記の手順では、CVE-2017-5753 のインスタンスを使用する場合と共に、FLUSH + RELOAD という手法を使用する例を示します。

## <a name="what-software-scenarios-can-be-impacted"></a>影響を受けるソフトウェアのシナリオ

[セキュリティ開発ライフサイクル](https://www.microsoft.com/sdl/)(SDL) のようなプロセスを使用してセキュリティで保護されたソフトウェアを開発するには、通常、開発者がアプリケーションに存在する信頼境界を特定する必要があります。 信頼境界は、システム上の別のプロセスや、カーネルモードのデバイスドライバーの場合は管理者以外のユーザーモードプロセスなど、信頼性の低いコンテキストによって提供されるデータをアプリケーションが操作する場所に存在します。 予測実行側チャネルを含む脆弱性の新しいクラスは、デバイス上のコードとデータを分離する既存のソフトウェアセキュリティモデルの信頼境界の多くに関連しています。

次の表は、開発者がこれらの脆弱性の発生を懸念する必要があるソフトウェアセキュリティモデルの概要を示しています。

|信頼境界|説明|
|----------------|----------------|
|仮想マシン境界 |別の仮想マシンから信頼されていないデータを受信する別の仮想マシン内のワークロードを分離するアプリケーションは、危険にさらされる可能性があります。|
|カーネル境界|管理者以外のユーザーモードプロセスから信頼されていないデータを受信するカーネルモードデバイスドライバーは、危険にさらされる可能性があります。|
|プロセス境界 |リモートプロシージャコール (RPC)、共有メモリ、またはその他の Inter-Process 通信 (IPC) メカニズムなどを使用して、ローカルシステムで実行されている別のプロセスから信頼されていないデータを受け取るアプリケーションは、危険にさらされる可能性があります。|
|エンクレーブ境界|エンクレーブの外部から信頼されていないデータを受信する secure エンクレーブ (Intel SGX など) 内で実行されるアプリケーションは、危険にさらされる可能性があります。|
|言語の境界|またはジャストインタイム (JIT) を解釈するアプリケーションは、より高いレベルの言語で記述された信頼できないコードをコンパイルして実行する可能性があります。|

上記の信頼境界のいずれかに公開されている攻撃対象のアプリケーションでは、攻撃対象領域のコードを確認して、予測実行側チャネルの脆弱性の可能性のあるインスタンスを特定し、軽減する必要があります。 リモートネットワークプロトコルなどのリモート攻撃サーフェイスにさらされる信頼境界は、予測実行側チャネルの脆弱性に対するリスクがあることを示すものではないことに注意してください。

## <a name="potentially-vulnerable-coding-patterns"></a>潜在的に脆弱なコーディングパターン

予測実行側チャネルの脆弱性は、複数のコーディングパターンの結果として発生する可能性があります。 このセクションでは、脆弱な可能性のあるコーディングパターンについて説明し、それぞれの例を示します。ただし、これらのテーマのバリエーションが存在する可能性があることを認識する必要があります。 このため、開発者はこれらのパターンを例として使用することをお勧めします。これは、潜在的に脆弱なコーディングパターンを網羅した一覧ではありません。 現在のソフトウェアに存在できるのと同じクラスのメモリの安全性の脆弱性は、バッファーオーバーラン、範囲外の配列のアクセス、初期化されていないメモリの使用、型の混乱などに限定されない、実行の予測および順序のないパスにも存在する可能性があります。 アーキテクチャパスに従って、攻撃者がメモリの安全性の脆弱性を悪用するために使用できるものと同じプリミティブが、予測パスにも適用される場合があります。

一般に、条件付き分岐 misprediction に関連する予測実行側チャネルは、条件式が、信頼度の低いコンテキストで制御または影響を受ける可能性のあるデータに対して動作する場合に発生する可能性があります。 たとえば、 **`if`** 、、 **`for`** 、、 **`while`** **`switch`** または三項ステートメントで使用される条件式を含めることができます。 これらの各ステートメントについて、コンパイラは、CPU が実行時にの分岐ターゲットを予測できる条件分岐を生成する場合があります。

各例では、開発者が軽減策としてバリアを導入できる場所に "投機バリア" という語句のコメントが挿入されます。 詳細については、「軽減策」を参照してください。

## <a name="speculative-out-of-bounds-load"></a>予測外の負荷

このようなコーディングパターンのカテゴリには、条件分岐の misprediction があります。これは、予測外のメモリアクセスにつながります。

### <a name="array-out-of-bounds-load-feeding-a-load"></a>配列の読み込み中に負荷が出てきた配列

このコーディングパターンは、CVE-2017-5753 (境界チェックのバイパス) で最初に記述された脆弱なコーディングパターンです。 この記事の背景セクションでは、このパターンについて詳しく説明します。

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ReadByte(unsigned char *buffer, unsigned int buffer_size, unsigned int untrusted_index) {
    if (untrusted_index < buffer_size) {
        // SPECULATION BARRIER
        unsigned char value = buffer[untrusted_index];
        return shared_buffer[value * 4096];
    }
}
```

同様に、配列の範囲外の読み込みは、misprediction が原因で終了状態を超えるループと組み合わせて発生する場合があります。 この例では、式に関連付けられている条件分岐は、 `x < buffer_size` が以上の場合にループの本体を予測ミス割合および投機的ことがあり **`for`** ます。その結果、予測 `x` `buffer_size` 外の負荷が発生します。

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ReadBytes(unsigned char *buffer, unsigned int buffer_size) {
    for (unsigned int x = 0; x < buffer_size; x++) {
        // SPECULATION BARRIER
        unsigned char value = buffer[x];
        return shared_buffer[value * 4096];
    }
}
```

### <a name="array-out-of-bounds-load-feeding-an-indirect-branch"></a>間接分岐に対する配列の範囲外の読み込み

このコーディングパターンでは、条件分岐 misprediction が関数ポインターの配列に対して範囲外のアクセスにつながる可能性があります。この場合、範囲外で読み取られたターゲットアドレスへの間接分岐が発生します。 次のスニペットは、この例を示しています。

この例では、パラメーターを使用して DispatchMessage に信頼されていないメッセージ識別子を指定してい `untrusted_message_id` ます。 `untrusted_message_id`がより小さい場合は `MAX_MESSAGE_ID` 、関数ポインターの配列にインデックスを作成し、対応する分岐ターゲットに分岐するために使用されます。 このコードは安全なアーキテクチャですが、CPU が条件分岐を起因した場合、値が以上の場合にによってインデックスが作成され、その結果、 `DispatchTable` `untrusted_message_id` `MAX_MESSAGE_ID` 範囲外のアクセスが発生する可能性があります。 これにより、投機的実行されるコードに応じて情報が漏えいする可能性のある、配列の境界を超えて派生したブランチターゲットアドレスからの予測実行が発生する可能性があります。

```cpp
#define MAX_MESSAGE_ID 16

typedef void (*MESSAGE_ROUTINE)(unsigned char *buffer, unsigned int buffer_size);

const MESSAGE_ROUTINE DispatchTable[MAX_MESSAGE_ID];

void DispatchMessage(unsigned int untrusted_message_id, unsigned char *buffer, unsigned int buffer_size) {
    if (untrusted_message_id < MAX_MESSAGE_ID) {
        // SPECULATION BARRIER
        DispatchTable[untrusted_message_id](buffer, buffer_size);
    }
}
```

配列の範囲外の読み込みによって別の負荷が発生した場合と同様に、この状態は、misprediction が原因で終了状態を超えるループと組み合わせて発生することもあります。

### <a name="array-out-of-bounds-store-feeding-an-indirect-branch"></a>間接分岐を出力する配列の範囲外のストア

前の例では、予測外の負荷が間接分岐ターゲットにどのように影響するかを示していましたが、範囲外のストアでは、関数ポインターや戻り先アドレスなどの間接分岐ターゲットを変更することもできます。 これにより、攻撃者が指定したアドレスから予測される実行が生じる可能性があります。

この例では、信頼されていないインデックスがパラメーターを介して渡され `untrusted_index` ます。 `untrusted_index`が配列の要素数 (256 要素) より小さい場合は、 `pointers` の指定されたポインター値 `ptr` が配列に書き込まれ `pointers` ます。 このコードは安全なアーキテクチャですが、CPU が条件分岐を起因した場合、 `ptr` スタックに割り当てられた配列の境界を越えて投機的が書き込まれる可能性があり `pointers` ます。 これにより、のリターンアドレスが破損する可能性が `WriteSlot` あります。 攻撃者がの値を制御できる場合 `ptr` 、予測 `WriteSlot` パスに沿ってが返されたときに、任意のアドレスから予測される実行が発生する可能性があります。

```cpp
unsigned char WriteSlot(unsigned int untrusted_index, void *ptr) {
    void *pointers[256];
    if (untrusted_index < 256) {
        // SPECULATION BARRIER
        pointers[untrusted_index] = ptr;
    }
}
```

同様に、という名前の関数ポインターのローカル変数が `func` スタックに割り当てられている場合は、 `func` 条件分岐 misprediction が発生したときにを参照するアドレスを投機的に変更することができます。 これにより、関数ポインターがによって呼び出されたときに、任意のアドレスからの予測実行が発生する可能性があります。

```cpp
unsigned char WriteSlot(unsigned int untrusted_index, void *ptr) {
    void *pointers[256];
    void (*func)() = &callback;
    if (untrusted_index < 256) {
        // SPECULATION BARRIER
        pointers[untrusted_index] = ptr;
    }
    func();
}
```

これらの両方の例には、スタック割り当て間接分岐ポインターの予測的な変更が含まれていることに注意してください。 また、グローバル変数、ヒープに割り当てられたメモリ、および一部の Cpu の読み取り専用メモリに対しても、予測的な変更が発生する可能性があります。 スタックに割り当てられたメモリの場合、Microsoft C++ コンパイラは、スタックに割り当てられた間接分岐ターゲットを投機的に変更するための手順を既に実行しています。たとえば、コンパイラのセキュリティ機能の一部として、バッファーがセキュリティ cookie に隣接して配置されるようにローカル変数を並べ替えることが [`/GS`](../build/reference/gs-buffer-security-check.md) できます。

## <a name="speculative-type-confusion"></a>予測型の混乱

このカテゴリは、予測型の混乱を招く可能性があるコーディングパターンを扱います。 これは、予測実行時に非アーキテクチャパスに沿って、不適切な型を使用してメモリにアクセスした場合に発生します。 条件分岐 misprediction と予測ストアバイパスはどちらも、予測型の混乱を招く可能性があります。

予測ストアバイパスの場合、コンパイラが複数の型の変数にスタック位置を再利用するシナリオでこのような状況が発生する可能性があります。 これは、型の変数のアーキテクチャストアがバイパスされる可能性があるため、 `A` `A` 変数が割り当てられる前に型の読み込みを投機的 execute に許可できるためです。 以前に格納された変数の型が異なる場合は、予測型の混乱の条件を作成できます。

条件分岐 misprediction の場合、次のコードスニペットを使用して、予測型の混乱を招く可能性のあるさまざまな条件を記述します。

```cpp
enum TypeName {
    Type1,
    Type2
};

class CBaseType {
public:
    CBaseType(TypeName type) : type(type) {}
    TypeName type;
};

class CType1 : public CBaseType {
public:
    CType1() : CBaseType(Type1) {}
    char field1[256];
    unsigned char field2;
};

class CType2 : public CBaseType {
public:
    CType2() : CBaseType(Type2) {}
    void (*dispatch_routine)();
    unsigned char field2;
};

// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ProcessType(CBaseType *obj)
{
    if (obj->type == Type1) {
        // SPECULATION BARRIER
        CType1 *obj1 = static_cast<CType1 *>(obj);

        unsigned char value = obj1->field2;

        return shared_buffer[value * 4096];
    }
    else if (obj->type == Type2) {
        // SPECULATION BARRIER
        CType2 *obj2 = static_cast<CType2 *>(obj);

        obj2->dispatch_routine();

        return obj2->field2;
    }
}
```

### <a name="speculative-type-confusion-leading-to-an-out-of-bounds-load"></a>予測型の混乱。範囲外の読み込みにつながる

このコーディングパターンでは、予測型の混乱によって、読み込まれた値が後続の読み込みアドレスにフィードする、範囲外または型を混同したフィールドアクセスが発生する場合があります。 これは、配列の範囲外のコーディングパターンに似ていますが、上記のように別のコーディングシーケンスを使用して示されます。 この例では、攻撃コンテキストによっ `ProcessType` て、型のオブジェクト `CType1` ( `type` フィールドはに等しい) を使用して、対象のコンテキストが複数回実行される可能性があり `Type1` ます。 これにより、最初のステートメントの条件分岐をトレーニングして、取得されていないことを予測する効果が得られ **`if`** ます。 攻撃を行うコンテキストは、型のオブジェクトを使用して、対象のコンテキストを実行させることができ `ProcessType` `CType2` ます。 これにより、最初のステートメントの条件分岐が起因され、 **`if`** ステートメントの本体が実行され **`if`** 、型のオブジェクトがにキャストされると、予測型の混乱が生じる可能性が `CType2` `CType1` あります。 `CType2`はよりも小さいため `CType1` 、へのメモリアクセスを使用すると、秘密である `CType1::field2` 可能性があるデータの範囲外の予測的な負荷が発生します。 この値は、 `shared_buffer` 前に説明した配列範囲外の例と同様に、から観測可能な副作用を作成できる読み込みで使用されます。

### <a name="speculative-type-confusion-leading-to-an-indirect-branch"></a>間接分岐につながる予測型の混乱

このコーディングパターンでは、予測型の混乱によって、予測実行中に unsafe 間接分岐が発生する可能性があります。 この例では、攻撃コンテキストによっ `ProcessType` て、型のオブジェクト `CType2` ( `type` フィールドはに等しい) を使用して、対象のコンテキストが複数回実行される可能性があり `Type2` ます。 これにより、最初に実行するステートメントの条件分岐をトレーニングし、ステートメントを実行しないようにすることができ **`if`** `else if` ます。 攻撃を行うコンテキストは、型のオブジェクトを使用して、対象のコンテキストを実行させることができ `ProcessType` `CType1` ます。 これにより、最初のステートメントの条件分岐で予測が発生 **`if`** し、 `else if` ステートメントが予測されなかった場合に、の本体を実行 `else if` し、型のオブジェクトをにキャストすると、予測型の混乱が生じる可能性が `CType1` `CType2` あります。 フィールドが `CType2::dispatch_routine` 配列と重複しているため **`char`** `CType1::field1` 、意図しない分岐ターゲットに対する予測間接分岐が発生する可能性があります。 攻撃を受けたコンテキストが配列内のバイト値を制御できる場合は `CType1::field1` 、ブランチターゲットアドレスを制御できる可能性があります。

## <a name="speculative-uninitialized-use"></a>予測されていない使用

このようなコーディングパターンのカテゴリには、予測実行が初期化されていないメモリにアクセスし、それを使用して後続の読み込みまたは間接分岐をフィードするシナリオが含まれます。 これらのコーディングパターンを悪用可能にするには、攻撃者が、使用されているコンテキストによって初期化されることなく、使用されるメモリの内容を制御または意味を与える必要があります。

### <a name="speculative-uninitialized-use-leading-to-an-out-of-bounds-load"></a>初期化されていない予測される使用により、範囲外の読み込みが発生する

初期化されていない使用によって、攻撃者によって制御される値を使用して、範囲外の負荷が生じる可能性があります。 次の例では、の値 `index` がすべてのアーキテクチャパスに割り当てられており、以下である `trusted_index` と想定されてい `trusted_index` `buffer_size` ます。 ただし、コンパイラによって生成されるコードによっては、予測ストアバイパスが発生する可能性があります。これにより、 `buffer[index]` および依存式からへの割り当ての前にを実行することができ `index` ます。 このような場合、の初期 `index` 化されていない値がのオフセットとして使用されます。これにより、 `buffer` 攻撃者は機密情報を範囲外に読み取り、の依存する負荷を通じて、この情報をサイドチャネル経由で伝達でき `shared_buffer` ます。

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

void InitializeIndex(unsigned int trusted_index, unsigned int *index) {
    *index = trusted_index;
}

unsigned char ReadByte(unsigned char *buffer, unsigned int buffer_size, unsigned int trusted_index) {
    unsigned int index;

    InitializeIndex(trusted_index, &index); // not inlined

    // SPECULATION BARRIER
    unsigned char value = buffer[index];
    return shared_buffer[value * 4096];
}
```

### <a name="speculative-uninitialized-use-leading-to-an-indirect-branch"></a>間接分岐につながる、初期化されていない予測される使用

初期化されていない使用は、ブランチターゲットが攻撃者によって制御される間接分岐につながる可能性があります。 次の例で `routine` は、 `DefaultMessageRoutine1` の値に応じて、がまたはのいずれかに割り当てられ `DefaultMessageRoutine` てい `mode` ます。 アーキテクチャパスでは、これにより、 `routine` 常に間接分岐の前に初期化されます。 ただし、コンパイラによって生成されるコードによっては、 `routine` に対する割り当ての前に間接分岐から投機的を実行することを許可する予測ストアバイパスが発生する可能性があり `routine` ます。 このような状況が発生した場合、攻撃者がの初期化されていない値に影響を与える可能性があると仮定して、任意のアドレスから実行を投機的ことができる場合があり `routine` ます。

```cpp
#define MAX_MESSAGE_ID 16

typedef void (*MESSAGE_ROUTINE)(unsigned char *buffer, unsigned int buffer_size);

const MESSAGE_ROUTINE DispatchTable[MAX_MESSAGE_ID];
extern unsigned int mode;

void InitializeRoutine(MESSAGE_ROUTINE *routine) {
    if (mode == 1) {
        *routine = &DefaultMessageRoutine1;
    }
    else {
        *routine = &DefaultMessageRoutine;
    }
}

void DispatchMessage(unsigned int untrusted_message_id, unsigned char *buffer, unsigned int buffer_size) {
    MESSAGE_ROUTINE routine;

    InitializeRoutine(&routine); // not inlined

    // SPECULATION BARRIER
    routine(buffer, buffer_size);
}
```

## <a name="mitigation-options"></a>対応策オプション

予測実行側チャネルの脆弱性は、ソースコードに変更を加えることで軽減できます。 これらの変更には、推定 *バリア* の追加や、予測実行から機密情報にアクセスできなくなるようにアプリケーションの設計を変更することによって、脆弱性の特定のインスタンスを軽減することが含まれる場合があります。

### <a name="speculation-barrier-via-manual-instrumentation"></a>手動インストルメンテーションを使用した投機バリア

開発者は、推定 *バリア* を手動で挿入して、非アーキテクチャパスに従って予測実行が行われないようにすることができます。 たとえば、開発者は、ブロックの先頭 (条件分岐の後) または問題のある最初の読み込みの前に、条件付きブロックの本体の危険なコーディングパターンの前に、投機バリアを挿入できます。 これにより、条件分岐 misprediction は、実行をシリアル化することで、非アーキテクチャパスで危険なコードを実行できなくなります。 次の表に示すように、投機バリアシーケンスはハードウェアアーキテクチャによって異なります。

|アーキテクチャ|CVE-2017-5753 に固有の投機バリア|CVE-2018-3639 に固有の投機バリア|
|----------------|----------------|----------------|
|x86/x64|_mm_lfence ()|_mm_lfence ()|
|ARM|現在使用できません|__dsb (0)|
|ARM64|現在使用できません|__dsb (0)|

たとえば、次のように組み込みを使用すると、次のコードパターンを軽減でき `_mm_lfence` ます。

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ReadByte(unsigned char *buffer, unsigned int buffer_size, unsigned int untrusted_index) {
    if (untrusted_index < buffer_size) {
        _mm_lfence();
        unsigned char value = buffer[untrusted_index];
        return shared_buffer[value * 4096];
    }
}
```

### <a name="speculation-barrier-via-compiler-time-instrumentation"></a>コンパイラ時間インストルメンテーションを使用した投機バリア

Visual Studio 2017 の Microsoft C++ コンパイラ (バージョン15.5.5 以降) にはスイッチがサポートされており、 `/Qspectre` これにより、CVE-2017-5753 に関連する潜在的に脆弱なコードパターンの限られたセットに対して、投機バリアが自動的に挿入されます。 フラグのドキュメントでは、 [`/Qspectre`](../build/reference/qspectre.md) その効果と使用方法について詳しく説明しています。 このフラグは、脆弱な可能性のあるコーディングパターンをすべて網羅しているわけではありません。そのため、このような開発者は、このクラスの脆弱性を包括的に軽減することはできません。

### <a name="masking-array-indices"></a>配列インデックスのマスク

予測外の負荷が発生する可能性がある場合は、配列インデックスを明示的にバインドするロジックを追加することで、アーキテクチャパスと非アーキテクチャパスの両方で配列インデックスを厳密に制限できます。 たとえば、2の累乗に固定されたサイズに配列を割り当てることができる場合、単純なマスクを導入できます。 このことを次のサンプルで示します。この例では、 `buffer_size` 2 の累乗にアラインされていると想定されています。 これにより `untrusted_index` `buffer_size` 、条件分岐 misprediction が発生し、が以上の値を使用して渡された場合でも、は常により小さくなり `untrusted_index` `buffer_size` ます。

ここで実行されるインデックスマスクは、コンパイラによって生成されるコードによっては、予測ストアのバイパスの対象になる可能性があることに注意してください。

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ReadByte(unsigned char *buffer, unsigned int buffer_size, unsigned int untrusted_index) {
    if (untrusted_index < buffer_size) {
        untrusted_index &= (buffer_size - 1);
        unsigned char value = buffer[untrusted_index];
        return shared_buffer[value * 4096];
    }
}
```

### <a name="removing-sensitive-information-from-memory"></a>メモリからの機密情報の削除

予測実行側チャネルの脆弱性を軽減するために使用できるもう1つの手法は、機密情報をメモリから削除することです。 ソフトウェア開発者は、予測実行中に機密情報にアクセスできないように、アプリケーションをリファクターする機会を探すことができます。 これは、アプリケーションの設計をリファクタリングして、機密情報を個別のプロセスに分離することによって実現できます。 たとえば、web ブラウザーアプリケーションでは、各 web オリジンに関連付けられたデータを個別のプロセスに分離して、1つのプロセスが予測実行によってクロスオリジンデータにアクセスできないようにすることができます。

## <a name="see-also"></a>関連項目

[予測実行のサイドチャネルの脆弱性を軽減するためのガイダンス](https://portal.msrc.microsoft.com/security-guidance/advisory/ADV180002)<br/>
[予測実行側チャネルハードウェアの脆弱性の軽減](https://blogs.technet.microsoft.com/srd/2018/03/15/mitigating-speculative-execution-side-channel-hardware-vulnerabilities/)
