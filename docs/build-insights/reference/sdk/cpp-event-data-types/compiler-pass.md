---
title: CompilerPass クラス
description: C++ Build Insights SDK の CompilerPass クラスのリファレンスです。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CompilerPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 054bdf75dcfca42b8c202565fb44df671f17f912
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831620"
---
# <a name="compilerpass-class"></a>CompilerPass クラス

::: moniker range="<=vs-2015"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=vs-2017"

`CompilerPass` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 これを使用して [BACK_END_PASS](../event-table.md#back-end-pass) または [FRONT_END_PASS](../event-table.md#front-end-pass) イベントを照合します。

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

その基底クラス [Activity](activity.md) から継承されたメンバーに加えて、`CompilerPass` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[CompilerPass](#compiler-pass)

### <a name="enums"></a>列挙型

#### <a name="passcode"></a>PassCode

|値|説明|
|-|-|
|FRONT_END|フロントエンド パス。|
|BACK_END|バックエンド パス。|

### <a name="functions"></a>関数

[InputSourcePath](#input-source-path)\
[OutputObjectPath](#output-object-path)\
[PassCode](#pass-code)\

## <a name="compilerpass"></a><a name="compiler-pass"></a> CompilerPass

```cpp
CompilerPass(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
[BACK_END_PASS](../event-table.md#back-end-pass) または [FRONT_END_PASS](../event-table.md#front-end-pass) イベント。

## <a name="inputsourcepath"></a><a name="input-source-path"></a> InputSourcePath

```cpp
const wchar_t* InputSourcePath() const;
```

### <a name="return-value"></a>戻り値

このコンパイラ パスによって処理された入力ソース ファイルへの絶対パス。

## <a name="outputobjectpath"></a><a name="output-object-path"></a> OutputObjectPath

```cpp
const wchar_t* OutputObjectPath() const;
```

### <a name="return-value"></a>戻り値

このコンパイラ パスによって生成された出力オブジェクト ファイルへの絶対パス。

## <a name="passcode"></a><a name="pass-code"></a> PassCode

```cpp
PassCode PassCode() const;
```

### <a name="return-value"></a>戻り値

この CompilerPass オブジェクトによって表されるコンパイラ パスを示すコード。

::: moniker-end
