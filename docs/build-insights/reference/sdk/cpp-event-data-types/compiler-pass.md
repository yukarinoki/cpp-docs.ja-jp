---
title: コンパイラパスクラス
description: C++ ビルド インサイト SDK コンパイラパス クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CompilerPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 11af981b647d5183f88dad024d90c0ef4f8a28bc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325041"
---
# <a name="compilerpass-class"></a>コンパイラパスクラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`CompilerPass`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) [BACK_END_PASS](../event-table.md#back-end-pass)または[FRONT_END_PASS](../event-table.md#front-end-pass)イベントに一致させるために使用します。

## <a name="syntax"></a>構文

```cpp
class CompilerPass : public Activity
{
public:
    enum class PassCode
    {
        FRONT_END,
        BACK_END
    };

    CompilerPass(const RawEvent& event);

    PassCode       PassCode() const;
    const wchar_t* InputSourcePath() const;
    const wchar_t* OutputObjectPath() const;
};
```

## <a name="members"></a>メンバー

クラスには、[その Activity](activity.md)基本クラスから継承された`CompilerPass`メンバーと共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[コンパイラパス](#compiler-pass)

### <a name="enums"></a>列挙体

#### <a name="passcode"></a>パスコード

|||
|-|-|
|FRONT_END|フロントエンドパス。|
|BACK_END|バックエンド パス。|

### <a name="functions"></a>関数

[ソースパス](#input-source-path)\
[オブジェクトパスを出力します。](#output-object-path)\
[パスコード](#pass-code)\

## <a name="compilerpass"></a><a name="compiler-pass"></a>コンパイラパス

```cpp
CompilerPass(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[BACK_END_PASS](../event-table.md#back-end-pass)イベントまたは[FRONT_END_PASS](../event-table.md#front-end-pass)イベント。

## <a name="inputsourcepath"></a><a name="input-source-path"></a>ソースパス

```cpp
const wchar_t* InputSourcePath() const;
```

### <a name="return-value"></a>戻り値

このコンパイラ パスによって処理される入力ソース ファイルへの絶対パス。

## <a name="outputobjectpath"></a><a name="output-object-path"></a>オブジェクトパスを出力します。

```cpp
const wchar_t* OutputObjectPath() const;
```

### <a name="return-value"></a>戻り値

このコンパイラ パスによって生成される出力オブジェクト ファイルへの絶対パス。

## <a name="passcode"></a><a name="pass-code"></a>パスコード

```cpp
PassCode PassCode() const;
```

### <a name="return-value"></a>戻り値

このコンパイラ パスオブジェクトによって表されるコンパイラ パスを示すコード。

::: moniker-end
