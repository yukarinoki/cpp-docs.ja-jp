---
title: シンボル名クラス
description: C++ ビルド インサイト SDK シンボル名 クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SymbolName
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1306fb43d6c2140a75b36c5f142532916cf26ae4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324353"
---
# <a name="symbolname-class"></a>シンボル名クラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`SymbolName`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) [SYMBOL_NAME](../event-table.md#symbol-name)イベントに一致させるために使用します。

## <a name="syntax"></a>構文

```cpp
class SymbolName : public SimpleEvent
{
public:
    SymbolName(const RawEvent& event);

    const unsigned long long&  Key() const;
    const char*                Name() const;
};
```

## <a name="members"></a>メンバー

[クラスには、SimpleEvent](simple-event.md)基本クラスから継承されたメンバーと`SymbolName`共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[シンボル名](#symbol-name)

### <a name="functions"></a>関数

[キー](#key)
[名](#name)

## <a name="key"></a><a name="key"></a>キー

```cpp
const unsigned long long& Key() const;
```

### <a name="return-value"></a>戻り値

このシンボルで表される型の数値識別子。 この識別子は、コンパイラのフロントエンド パス内で一意です。

## <a name="name"></a><a name="name"></a>名前

```cpp
const char* Name() const;
```

### <a name="return-value"></a>戻り値

シンボルで表される型の名前です。

## <a name="symbolname"></a><a name="symbol-name"></a>シンボル名

```cpp
SymbolName(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[SYMBOL_NAME](../event-table.md#symbol-name)イベント。

::: moniker-end
