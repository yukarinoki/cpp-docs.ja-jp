---
title: 予測の実行側チャネルの C++ 開発者ガイド |Microsoft ドキュメント
ms.custom: ''
ms.date: 05/21/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, security
- security [C++]
- security [C++], best practices
- Spectre
- CVE-2017-5753
- Speculative Execution
author: mamillmsft
ms.author: mikeblome
ms.workload:
- cplusplus
ms.openlocfilehash: 515e2223e67d86da12488d9880a1a0a258fc4bdf
ms.sourcegitcommit: 4b2c3b0c720aef42bce7e1e5566723b0fec5ec7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2018
ms.locfileid: "34428711"
---
# <a name="c-developer-guidance-for-speculative-execution-side-channels"></a>予測の実行側チャネルの C++ 開発者ガイド

この記事を識別および C++ のソフトウェアの予測の実行側チャネルのハードウェア脆弱性の軽減を支援する開発者向けガイダンスが含まれています。 これらの脆弱性は、信頼の境界を越えて機密情報を開示することができ、命令の予測、順序不定な実行をサポートするプロセッサで実行されているソフトウェアに影響を与えることができます。 上の脆弱性には、このクラスが 1 年 1 月、2018年」に記載し、追加の背景情報とガイダンスは含まれて[マイクロソフト セキュリティ アドバイザリ](https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/ADV180002)です。

この記事で提供されたガイダンスは上の脆弱性によって表されるクラスに関連します。

1. CVE-2017-5753、Spectre バリアント 1 とも呼ばれます。 このハードウェアの脆弱性のクラスは、条件付き分岐 misprediction 結果として発生する予測の実行のために発生する側のチャネルに関連付けられます。 Visual Studio 2017 年 1 (バージョン 15.5.5 以降) の Visual C コンパイラにはサポートが含まれています、 `/Qspectre` CVE 2017-5753 に関連する可能性のある脆弱なコーディング パターンの限られた一連のコンパイル時の軽減策を提供するスイッチです。 ドキュメントを[/Qspectre](https://docs.microsoft.com/en-us/cpp/build/reference/qspectre)フラグは、その効果と使用状況の詳細についてを提供します。

2. CVE-2018-3639 とも呼ばれる[予測ストア バイパス (SSB)](https://aka.ms/sescsrdssb)です。 このハードウェアの脆弱性のクラスは、メモリ アクセス misprediction の結果として依存ストア事前負荷の予測の実行のために発生する側のチャネルに関連付けられます。

という名前のプレゼンテーションの予測の実行側チャネル上の脆弱性の概要についてはアクセスが見つかりません[、Spectre ケースとメルトダウン](https://www.youtube.com/watch?v=_4O0zMW-Zu4)によってこれらの問題を検出する research チームのいずれか。

## <a name="what-are-speculative-execution-side-channel-hardware-vulnerabilities"></a>予測の実行側チャネル ハードウェア上の脆弱性とは

最新 Cpu より高度なパフォーマンスを提供することにより命令が予測し、順序不定な実行を使用します。 たとえば、多くの場合、これは、CPU 投機的予測されたブランチ ターゲットでの命令の実行を開始することができます (条件付きおよび間接) の分岐のターゲットを予測する実際の分岐の対象になるまで、stall を回避解決されます。 イベントで後で、CPU は、misprediction が発生したことを検出、投機的に計算されたマシンの状態のすべては破棄されます。 これにより、リタイアメント推理のアーキテクチャ上に表示される影響はありません。

その予測の実行は、アーキテクチャの表示の状態に影響しません、残存のトレース、CPU で使用されるさまざまなキャッシュなどのアーキテクチャではない状態にせずにします。 これらの残存トレース側チャネル上の脆弱性に上昇を提供できる予測の実行のすることをお勧めします。 これを理解、CVE 2017 5753 (境界チェックのバイパス) の例を提供する次のコード フラグメントを考慮してください。

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

この例では`ReadByte`がそのバッファーにバッファー、バッファー サイズ、およびインデックスを指定します。 指定したとおり、インデックス パラメーター `untrusted_index`、小によって提供される、管理者以外のプロセスなど、特権コンテキスト。 場合`untrusted_index`はより小さい`buffer_size`からそのインデックスにある文字が読み込まれる`buffer`によって参照されるメモリの共有領域を使用するインデックスと`shared_buffer`です。 

アーキテクチャの観点から、このコード シーケンスは完全に安全にすることは保証されて`untrusted_index`は常により小さい`buffer_size`です。 ただし、予測の実行が存在する場合は、CPU が条件付き分岐の mispredict および if の本体は実行が可能な場合でも、ステートメント`untrusted_index`がより大きいまたは等しい`buffer_size`です。 このため、CPU 投機的を読み取ることが、バイトの境界外`buffer`(シークレットがある可能性があります) を使用して、そのバイト値を以降の読み込みのアドレスを計算および`shared_buffer`です。 

残存の副作用をから境界外に読み取られたバイトの値に関する情報を公開する CPU キャッシュに残ることが CPU には、この misprediction 検出最終的には、中に`buffer`です。 副作用は小で検出できる特権コンテキストがどの程度の速度を調査して、システムで実行されている各キャッシュ線`shared_buffer`にアクセスします。 このために実行できる手順は次のとおりです。

1. **呼び出す`ReadByte`で複数回`untrusted_index`されているより小さい`buffer_size`** です。 攻撃のコンテキストには、対象コンテキストを呼び出す可能性があります`ReadByte`(RPC) 経由などとして not 取得するブランチ予測子であるようなトレーニングを受けた`untrusted_index`はより小さい`buffer_size`です。

2. **内のすべてのキャッシュ行をフラッシュ`shared_buffer`** です。 攻撃のコンテキストはすべての共有によって参照されるメモリの領域にキャッシュ行をフラッシュする必要があります`shared_buffer`です。 メモリ領域を共有すると、ためこれは簡単でありなどの組み込み関数を使用して実現できます`_mm_clflush`です。

3. **呼び出す`ReadByte`で`untrusted_index`以上である`buffer_size`** です。 攻撃のコンテキストにより、対象コンテキストを呼び出す`ReadByte`よう正しくを予測していないこと、分岐が実行されます。 このプロセッサ投機的 if の本体は実行をブロックすると、`untrusted_index`以上である`buffer_size`、したがって読み取り範囲外に先頭の`buffer`です。 その結果、`shared_buffer`しまい、CPU によって読み込まれるそれぞれのキャッシュ ラインに範囲外、読み取られた可能性があるシークレットの値を使用してインデックスが作成されます。

4. **場合は、各キャッシュ行を読み取り`shared_buffer`これが最も迅速にアクセスして**です。 攻撃のコンテキストでキャッシュの各行を読み取ることができる`shared_buffer`し、その他のよりも大幅に高速読み込みのキャッシュ ラインを検出します。 これは、手順 3 取り込まれましたと思われるキャッシュ ラインです。 この例ではバイト値とキャッシュの線の間に一対一のリレーションシップがないため、これにより、攻撃者が範囲外に読み取られたバイトの実際の値を推論します。

上記の手順では、CVE 2017-5753 のインスタンスを悪用すると共に、フラッシュ + 再読み込みと呼ばれる手法を使用する例を提供します。

## <a name="what-software-scenarios-can-be-impacted"></a>どのようなソフトウェアのシナリオの影響を受けることができますか。

ようにプロセスを使用してセキュリティで保護されたソフトウェアの開発、[セキュリティ開発ライフ サイクル](https://www.microsoft.com/en-us/sdl/)(SDL) には、通常、アプリケーション内に存在する信頼の境界を識別する開発者が必要です。 信頼の境界は、アプリケーションがシステム上の別のプロセスまたはカーネル モード デバイス ドライバーの場合、管理者以外のユーザー モード プロセスなどの信頼度の低いコンテキストによって提供されるデータをやり取りの場所に存在します。 上の脆弱性の予測の実行側チャネルに関連する新しいクラスは、さまざまなコードと、デバイス上のデータを分離する既存のソフトウェアのセキュリティ モデル内の信頼境界に関連します。 

次の表は、開発者が発生しているこれらの脆弱性を考慮する必要があります、ソフトウェアのセキュリティ モデルの概要を示します。

|信頼の境界|説明|
|----------------|----------------|
|仮想マシンの境界|危険にさらされて信頼できないデータを別の仮想マシンから受信する別の仮想マシンでワークロードを分離するアプリケーションがあります。| 
|カーネル境界|管理者以外のユーザー モード プロセスから信頼されていないデータを受信するカーネル モード デバイス ドライバーは、危険にさらさ可能性があります。| 
|プロセス境界|を介して、リモート プロシージャ コール (RPC)、共有メモリ、またはその他のプロセス間通信 (IPC) メカニズムが危険にさらされる可能性がありますなど、ローカルのシステムで実行されている別のプロセスから信頼されていないデータを受信するアプリケーション。|
|Enclave 境界|危険にさらされてから、enclave の外部の信頼されていないデータを受信する (Intel SGX) などのセキュリティで保護された enclave 内で実行するアプリケーションがあります。|
|言語の境界|解釈するアプリケーションまたは Just-In-Time (JIT) コンパイルし、実行はで記述されたコードが信頼されていない上位レベルの言語が危険にさらされる可能性があります。|

攻撃対象領域の公開、上記のいずれかの信頼の境界がコードを特定し、可能なインスタンスの予測の実行側チャネルの脆弱性の軽減、攻撃を確認する必要がありますのあるアプリケーション。 予測の実行側チャネル上の脆弱性の危険にさらされるをリモートのネットワーク プロトコルなどのリモートの攻撃対象領域に公開されている信頼の境界が示されたいないことに注意してください。

## <a name="potentially-vulnerable-coding-patterns"></a>可能性のある脆弱なコーディング パターン

予測の実行側チャネル上の脆弱性は、複数のコーディング パターンの結果として発生します。 このセクションでは、可能性のある脆弱なコーディング パターンについて説明し、それぞれの例を示しますが、これらのテーマでのバリエーションがありますが認識される必要があります。 そのため、開発者は例とは、排他的なリストのすべての脆弱性が潜んでコーディング パターンではなく、これらのパターンをお勧めします。

一般に、予測の実行側チャネルの関連する条件付き分岐 misprediction が生じる場合、条件式の制御したりできる信頼性の低いコンテキストによって影響を受けるデータを操作します。 たとえば、これで使用する条件付きの式を含めることができます`if`、 `for`、 `while`、 `switch`、または 3 項ステートメントです。 これらのステートメントごとに、コンパイラは、CPU が実行時の分岐ターゲットを予測可能性がありますしを条件付き分岐を生成可能性があります。

それぞれの例では、開発者が緩和策としての障害を引き起こす可能性がある「推理バリア」という語句でコメントが挿入されます。 緩和策のセクションで詳しく説明しています。

## <a name="speculative-out-of-bounds-load"></a>範囲外の予測を読み込む

このカテゴリのコーディング パターンでは範囲外、予測するための条件分岐 misprediction メモリへのアクセス。

### <a name="array-out-of-bounds-load-feeding-a-load"></a>範囲外の配列は、負荷が供給することを読み込む

このコーディング パターンは、最初に記載されている脆弱なコーディング パターン CVE 2017 5753 (境界チェックのバイパス) 用です。 この記事の「バック グラウンドでは、このパターンの詳細について説明します。

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

同様に、配列範囲外の終了値を超えているループと共に負荷が発生する条件を misprediction のためです。 この例では、条件付き分岐に関連付けられている、`x < buffer_size`式が mispredict し、投機的の本体は実行、`for`ときにループ`x`がより大きいまたは等しい`buffer_size`、したがってその結果、予測に範囲外を読み込みます。

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ReadBytes(unsigned char *buffer, unsigned int buffer_size) {
    for (unsigned int x = 0; x < buffer_size; x++) {
        // SPECULATION BARRIER
        unsigned char value = buffer[untrusted_index];
        return shared_buffer[value * 4096];
    }
}
```

### <a name="array-out-of-bounds-load-feeding-an-indirect-branch"></a>範囲外の配列が間接分岐供給することを読み込む

このコーディング パターンでは、条件付き分岐 misprediction 発生する可能性がの場合、ターゲットへの間接の分岐にし、潜在顧客に対応する関数ポインターの配列へのアクセスが範囲外に読み取られた範囲外です。 次のスニペットは、その方法を示す例を示します。 

この例では、信頼されていないメッセージの識別子はでもないときに提供、`untrusted_message_id`パラメーター。 場合`untrusted_message_id`はより小さい`MAX_MESSAGE_ID`、関数ポインターの配列インデックスを作成し、分岐を使用し、対応するブランチ ターゲットです。 このコードは、アーキテクチャとしては、セーフである場合は、CPU では、条件付きのブランチ予測ミス、でしたによりに`DispatchTable`によってインデックスが作成される`untrusted_message_id`その値がより大きいまたは等しいの場合`MAX_MESSAGE_ID`、そのために、範囲外にアクセスします。 これは、結果、投機的に実行されるコードによって情報の漏えいを招く可能性がある配列の境界を超えて派生したブランチ ターゲット アドレスから実行を予測します。

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

配列の範囲外の大文字と小文字の別の負荷を供給ロードされ、このような状況も、misprediction によりその終了条件を超えるループと共に発生します。

## <a name="speculative-type-confusion"></a>予測型の混乱

このカテゴリは、コーディング、予測型の混乱を得ることができますパターンを処理します。 これは、予測の実行中にないアーキテクチャをパスに沿って正しくない型を使用してメモリにアクセスするときに発生します。 条件付き分岐 misprediction と予測ストア バイ パスの両方招く予測型の混乱します。 

予測のストアの回避、コンパイラが複数の型の変数のスタックの場所で再利用のシナリオでこれが発生する可能性があります。 これは、アーキテクチャのストア型の変数の`A`バイパス可能性がありますので、型のロード`A`投機的変数が割り当てられる前に実行します。 以前に格納された変数が、別の種類は場合、は、予測型の混乱の条件を作成このことができます。

条件付き分岐 misprediction を記述する次のコード スニペットが使用する予測型の混乱を与えることができるさまざまな条件が増加します。

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

### <a name="speculative-type-confusion-leading-to-an-out-of-bounds-load"></a>予測の種類の混乱を先頭に範囲外を読み込む

このコーディング パターンでは、予測型の混乱がの場合、範囲外または読み込まれた値が後続の読み込みアドレスをフィード型混同フィールドにアクセスします。 これは配列の範囲外のコーディング パターンに似ていますが、代わりに上記のように、シーケンスをコーディングを生じます。 この例では、攻撃のコンテキストの対象コンテキストを実行する可能性があります`ProcessType`型のオブジェクトを複数回`CType1`(`type`フィールドと等しい`Type1`)。 最初の条件付き分岐のトレーニングの効果があります`if`ステートメントを作成した予測できません。 攻撃のコンテキストとの対象コンテキストを実行することができます、`ProcessType`型のオブジェクトと`CType2`です。 これは、結果、予測型の混乱場合は、最初の条件付き分岐`if`ステートメントを選択し、予測ミスの本体が実行、`if`ステートメントでは、したがって型のオブジェクトをキャスト`CType2`に`CType1`です。 `CType2`よりも小さい`CType1`へのメモリ アクセス`CType1::field2`は、予測の結果範囲外の読み込みシークレット可能性のあるデータ。 読み込みでこの値を使用して`shared_buffer`副作用を作成するには、配列と同様の例が既に説明した範囲外です。

### <a name="speculative-type-confusion-leading-to-an-indirect-branch"></a>間接的なブランチにつながる予測型混乱

このコーディング パターンには、予測型の混乱されることが unsafe 間接ブランチ予測の実行中に大文字と小文字が含まれます。 この例では、攻撃のコンテキストの対象コンテキストを実行する可能性があります`ProcessType`型のオブジェクトを複数回`CType2`(`type`フィールドと等しい`Type2`)。 最初の条件付き分岐のトレーニングの効果があります`if`ステートメントを実行して、`else if`ステートメントを実行できません。 攻撃のコンテキストとの対象コンテキストを実行することができます、`ProcessType`型のオブジェクトと`CType1`です。 これは、結果、予測型の混乱場合は、最初の条件付き分岐`if`ステートメントを予測実行されると、`else if`の本体を実行するステートメントがない抜けた予測するため、 `else if` の型のオブジェクトをキャストし、`CType1`に`CType2`です。 以降、`CType2::dispatch_routine`フィールドと重複しています、`char`配列`CType1::field1`、この結果、予測の間接的なブランチを意図していない分岐ターゲットにします。 攻撃のコンテキスト内のバイト値を制御できるかどうか、`CType1::field1`配列を受けることもできますブランチ ターゲット アドレスを制御します。

## <a name="speculative-uninitialized-use"></a>予測の初期化されていない使用

このカテゴリ コーディング パターンにはでは、予測の実行可能性があります初期化されていないメモリにアクセスしていて、後続の負荷または間接の分岐をフィードに使用が含まれます。 攻撃されるこれらのコーディング パターン、攻撃者を制御したり、明確で使用されているコンテキストで初期化されずに使用されるメモリの内容に影響を与えることができる必要があります。

### <a name="speculative-uninitialized-use-leading-to-an-out-of-bounds-load"></a>予測の初期化されていない使用につながる、範囲外の読み込み

予測の初期化されていない使用招く、範囲外読み込む攻撃者の制御値を使用します。 値以下の例で`index`が割り当てられている`trusted_index`アーキテクチャ上のすべてのパスでと`trusted_index`以下にあると見なされます`buffer_size`です。 ただし、コンパイラによって生成されるコード、に応じて可能であれば予測ストア バイパス行うことができるからの読み込みを許可する`buffer[index]`と依存する式への割り当てを事前に実行する`index`です。 このような場合に初期化されていない値を`index`へのオフセットとして使用される`buffer`される、攻撃者が範囲外の機密情報を閲覧してこれを伝えるための依存の読み込みを通じて側チャネルを介して`shared_buffer`.

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

### <a name="speculative-uninitialized-use-leading-to-an-indirect-branch"></a>間接の分岐に先行する予測の初期化されていない使用

予測の初期化されていない使用可能性のあるにつながります間接ブランチ分岐ターゲットが攻撃者によって制御されます。 次の例で`routine`いずれかに割り当てられている`DefaultMessageRoutine1`または`DefaultMessageRoutine`の値に応じて`mode`です。 アーキテクチャ上のパスでは、その結果`routine`常に、間接分岐の前の初期化中です。 ただし、コンパイラによって生成されるコード、に応じて予測ストア バイパスが発生するを通じて間接的なブランチを許可する`routine`への割り当てを事前に実行される投機的`routine`です。 このような場合、攻撃者ができる場合があります投機的からを実行する任意のアドレス、攻撃者が影響を与えるまたはの初期化されていない値を制御を想定して`routine`です。

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

## <a name="mitigation-options"></a>軽減オプション

ソース コードを変更することは、予測の実行側チャネル上の脆弱性を軽減できます。 これらの変更にはなどが含まれますなど、追加することによって、脆弱性の特定のインスタンスを緩和する、*推理バリア*、または機密情報にアクセスできないように予測に対するアプリケーションのデザインを変更すること実行します。

### <a name="speculation-barrier-via-manual-instrumentation"></a>手動のインストルメンテーションを使用して推理バリア

A*推理バリア*アーキテクチャではないパスに沿って進むから予測の実行を防ぐために開発者によって手動で挿入できます。 たとえば、開発者は、(条件付きのブランチ) の後のブロックの先頭にいずれかの条件付きブロックの本体での危険なコーディング パターンの前に推理バリアを挿入できますまたは重大な問題は、最初の読み込みの前にします。 これにより、コードを実行する、危険なアーキテクチャではないパスの実行をシリアル化して条件付き分岐 misprediction ができなくなります。 推理バリア シーケンスは、次の表の説明に従ってハードウェア アーキテクチャによって異なります。

|アーキテクチャ|推理バリア CVE 2017-5753 の組み込み|推理バリア CVE 2018-3639 の組み込み|
|----------------|----------------|----------------|
|x86 と x64|_mm_lfence()|_mm_lfence()|
|ARM|現在使用できません。|__dsb(0)|
|ARM64|現在使用できません。|__dsb(0)|

使用して、次のコード パターンを軽減するなど、`_mm_lfence`組み込みの次のようにします。

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

### <a name="speculation-barrier-via-compiler-time-instrumentation"></a>コンパイラにインストルメンテーションを使用して推理バリア

Visual Studio 2017 年 1 (バージョン 15.5.5 以降) の Visual C コンパイラにはサポートが含まれています、 `/Qspectre` CVE 2017-5753 に関連する可能性のある脆弱なコーディング パターンの限られた一連の推理バリアを自動的に挿入するスイッチです。 ドキュメントを[/Qspectre](https://docs.microsoft.com/en-us/cpp/build/reference/qspectre)フラグは、その効果と使用状況の詳細についてを提供します。 ことが重要よう開発者に依存しないように、このクラスの脆弱性の包括的な緩和策として、このフラグは取り上げませんのすべての脆弱性が潜んでコーディング パターンに注意してください。

## <a name="masking-array-indices"></a>配列のインデックスをマスク

ここで、予測の範囲外を読み込む場合に発生し、配列インデックス強くを制限できますアーキテクチャと非アーキテクチャの両方のパスの配列インデックスが明示的にバインドするためのロジックを追加することで。 たとえば、2 の累乗に配置されるサイズには、配列を割り当てることができる場合、単純なマスクを導入できます。 場所のように仮定の次の例に示す`buffer_size`は 2 の累乗に配置します。 これにより、`untrusted_index`は常により小さい`buffer_size`条件付き分岐 misprediction が発生した場合でも、および`untrusted_index`より大きいか等しいを値で渡された`buffer_size`です。

次に実行されるインデックスのマスクがある場合、コンパイラによって生成されるコードに応じて予測ストア バイパスされる可能性がありますに注意してください。

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

## <a name="removing-sensitive-information-from-memory"></a>機密情報をメモリから削除します。

予測の実行側チャネル上の脆弱性を軽減するために使用できるもう 1 つの方法では、メモリから機密情報を削除します。 ソフトウェア開発者は、予測の実行中に機密情報にアクセスできなくなっているように、アプリケーションをリファクターする機会を検索できます。 これは、別個のプロセスに機密性の高い情報を分離するアプリケーションのデザインをリファクタリングすることにより実現できます。 たとえば、web ブラウザー アプリケーションは、各 web オリジンを 1 つのプロセスが予測を実行してクロス オリジン データにアクセスできるように、別のプロセスに関連付けられたデータの分離を試行できます。

## <a name="see-also"></a>関連項目

[予測の実行サイド チャネル上の脆弱性を軽減するためにガイダンス](https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/ADV180002)
[予測実行側チャネル ハードウェア上の脆弱性を軽減します。](https://blogs.technet.microsoft.com/srd/2018/03/15/mitigating-speculative-execution-side-channel-hardware-vulnerabilities/)