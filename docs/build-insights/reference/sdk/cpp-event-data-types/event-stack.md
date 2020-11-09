---
title: EventStack クラス
description: C++ Build Insights SDK の EventStack クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EventStack
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b4f1e92011acdf8272fe631843c03c2f960a1234
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920711"
---
# <a name="eventstack-class"></a>EventStack クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`EventStack` クラスは [Event](event.md) オブジェクトのコレクションです。 C++ Build Insights SDK から受信するすべてのイベントは、`EventStack` オブジェクトの形式で取得されます。 このスタックの最後のエントリは、現在処理中のイベントです。 最後のエントリの前にあるエントリは、現在のイベントの親階層です。 C++ Build Insights で使用されるイベント モデルの詳細については、[イベント テーブル](../event-table.md)に関する記事を参照してください。

## <a name="syntax"></a>構文

```cpp
class EventStack
{
public:
    EventStack(const EVENT_COLLECTION_DATA& data);

    size_t      Size() const;
    RawEvent    Back() const;
    RawEvent    operator[] (size_t index) const;
};
```

## <a name="members"></a>メンバー

### <a name="constructors"></a>コンストラクター

[EventStack](#event-stack)

### <a name="functions"></a>機能

[Back](#back)
[operator[]](#subscript-operator)
[Size](#size)

## <a name="back"></a><a name="back"></a> Back

```cpp
RawEvent Back() const;
```

### <a name="return-value"></a>戻り値

スタックの最後のエントリを表す [RawEvent](raw-event.md) オブジェクト。 イベント スタックの最後のエントリは、トリガーされたイベントです。

## <a name="eventstack"></a><a name="event-stack"></a> EventStack

```cpp
EventStack(const EVENT_COLLECTION_DATA& data);
```

### <a name="parameters"></a>パラメーター

*data*\
`EventStack` の作成元である生データ。

### <a name="remarks"></a>注釈

通常、`EventStack` オブジェクトを自分で作成する必要はありません。 これらは、分析または再ログ記録セッション中にイベントが処理されているときに、C++ Build Insights SDK によって提供されます。

## <a name="operator"></a><a name="subscript-operator"></a> operator[]

```cpp
RawEvent operator[] (size_t index) const;
```

### <a name="parameters"></a>パラメーター

*index*\
イベント スタック内でアクセスする要素のインデックス。

### <a name="return-value"></a>戻り値

イベント スタック内の *index* によって示される位置に格納されているイベントを表す [RawEvent](raw-event.md) オブジェクト。

## <a name="size"></a><a name="size"></a> サイズ

```cpp
size_t Size() const;
```

### <a name="return-value"></a>戻り値

イベント スタックのサイズ。

::: moniker-end
