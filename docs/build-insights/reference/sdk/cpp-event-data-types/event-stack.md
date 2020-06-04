---
title: イベントスタッククラス
description: C++ ビルド インサイト SDK イベントスタック クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EventStack
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: eaaaedcbf57fdaf8e437a80a7823488febac3e1d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324974"
---
# <a name="eventstack-class"></a>イベントスタッククラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`EventStack`は[Event](event.md)オブジェクトのコレクションです。 C++ ビルドインサイト SDK から受信したすべてのイベントは、オブジェクトの`EventStack`形式で取得されます。 このスタックの最後のエントリは、現在処理中のイベントです。 最後のエントリの前にあるエントリは、現在のイベントの親階層です。 C++ ビルドインサイトで使用されるイベント モデルの詳細については、[イベントテーブル](../event-table.md)を参照してください。

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

[イベントスタック](#event-stack)

### <a name="functions"></a>関数

[バック](#back)
[演算子[]](#subscript-operator)
[サイズ](#size)

## <a name="back"></a><a name="back"></a>戻る

```cpp
RawEvent Back() const;
```

### <a name="return-value"></a>戻り値

スタックの最後のエントリを表す[RawEvent](raw-event.md)オブジェクト。 イベント スタックの最後のエントリは、トリガーされたイベントです。

## <a name="eventstack"></a><a name="event-stack"></a>イベントスタック

```cpp
EventStack(const EVENT_COLLECTION_DATA& data);
```

### <a name="parameters"></a>パラメーター

*データ*\
が作成`EventStack`される生データ。

### <a name="remarks"></a>解説

通常、オブジェクトを自分で構築`EventStack`する必要はありません。 分析または再ログ セッション中にイベントが処理されるときに、C++ ビルドインサイト SDK によって提供されます。

## <a name="operator"></a><a name="subscript-operator"></a>演算子[]

```cpp
RawEvent operator[] (size_t index) const;
```

### <a name="parameters"></a>パラメーター

*インデックス*\
イベント スタックでアクセスする要素のインデックス。

### <a name="return-value"></a>戻り値

イベント スタック内の*インデックス*で示される位置に格納されているイベントを表す[RawEvent](raw-event.md)オブジェクト。

## <a name="size"></a><a name="size"></a> サイズ

```cpp
size_t Size() const;
```

### <a name="return-value"></a>戻り値

イベント スタックのサイズ。

::: moniker-end
