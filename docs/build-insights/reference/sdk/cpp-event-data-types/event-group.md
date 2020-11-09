---
title: EventGroup クラス
description: C++ Build Insights SDK の EventGroup クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EventGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 57cbc7a053132909149aee182b9560e2ee33c161
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923309"
---
# <a name="eventgroup-class"></a>EventGroup クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`EventGroup` クラス テンプレートは、すべてのグループ キャプチャ クラスに対する基底クラスです。

## <a name="syntax"></a>構文

```cpp
template <typename TActivity>
class EventGroup;
{
public:
    size_t Size() const;

    const TActivity& operator[](size_t index) const;
    const TActivity& Front() const;
    const TActivity& Back() const;

    std::deque<TActivity>::const_iterator begin() const;
    std::deque<TActivity>::const_iterator end() const;
};
```

### <a name="parameters"></a>パラメーター

*TActivity* グループに含まれるアクティビティの種類。

## <a name="members"></a>メンバー

### <a name="functions"></a>機能

[Back](#back)
[begin](#begin)
[end](#end)
[Front](#front)
[operator[]](#subscript-operator)
[Size](#size)

## <a name="back"></a><a name="back"></a> Back

```cpp
const TActivity& Back() const;
```

### <a name="return-value"></a>戻り値

グループ内の最後のアクティビティ イベントへの参照。

## <a name="begin"></a><a name="begin"></a> begin

```cpp
std::deque<TActivity>::const_iterator begin() const;
```

### <a name="return-value"></a>戻り値

アクティビティ イベント グループの先頭を指す反復子。

## <a name="end"></a><a name="end"></a> end

```cpp
std::deque<TActivity>::const_iterator end() const;
```

### <a name="return-value"></a>戻り値

アクティビティ イベント グループの末尾の 1 つ後ろの位置を指す反復子。

## <a name="front"></a><a name="front"></a> Front

```cpp
const TActivity& Front() const;
```

### <a name="return-value"></a>戻り値

グループ内の最初のアクティビティ イベントへの参照。

## <a name="operator"></a><a name="subscript-operator"></a> operator[]

```cpp
const TActivity& operator[](size_t index) const;
```

### <a name="parameters"></a>パラメーター

*index*\
アクティビティ イベント グループ内でアクセスする要素のインデックス。

### <a name="return-value"></a>戻り値

*index* によって示される位置に格納されている、イベント スタックからのイベント。

## <a name="size"></a><a name="size"></a> サイズ

```cpp
size_t Size() const;
```

### <a name="return-value"></a>戻り値

イベント グループのサイズ。

::: moniker-end
