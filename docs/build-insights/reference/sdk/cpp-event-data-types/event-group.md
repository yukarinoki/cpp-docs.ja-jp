---
title: イベントグループクラス
description: C++ ビルド インサイト SDK イベントグループ クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EventGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 596c18ca0e9b4d7b26c4ed5209b16871952c4af2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324989"
---
# <a name="eventgroup-class"></a>イベントグループクラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`EventGroup`テンプレートは、すべてのグループ キャプチャ クラスの基本クラスです。

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

*活動*グループに含まれる活動タイプ。

## <a name="members"></a>メンバー

### <a name="functions"></a>関数

[バック](#back)
[・始](#begin)
[めのフロントエンド](#end)
[Front](#front)[operator[]](#subscript-operator)
[Size](#size)・オペレーター [] サイズ


## <a name="back"></a><a name="back"></a>戻る

```cpp
const TActivity& Back() const;
```

### <a name="return-value"></a>戻り値

グループ内の最後のアクティビティ イベントへの参照。

## <a name="begin"></a><a name="begin"></a>開始

```cpp
std::deque<TActivity>::const_iterator begin() const;
```

### <a name="return-value"></a>戻り値

アクティビティ イベント グループの先頭を指す反復器。

## <a name="end"></a><a name="end"></a>終わり

```cpp
std::deque<TActivity>::const_iterator end() const;
```

### <a name="return-value"></a>戻り値

アクティビティ イベント グループの末尾を 1 つ越えて 1 つ上の位置を指す反復器。

## <a name="front"></a><a name="front"></a>フロント

```cpp
const TActivity& Front() const;
```

### <a name="return-value"></a>戻り値

グループ内の最初のアクティビティ イベントへの参照。

## <a name="operator"></a><a name="subscript-operator"></a>演算子[]

```cpp
const TActivity& operator[](size_t index) const;
```

### <a name="parameters"></a>パラメーター

*インデックス*\
アクティビティ イベント グループ内でアクセスする要素のインデックス。

### <a name="return-value"></a>戻り値

*index*で示された位置に格納されているイベント スタックからのイベント。

## <a name="size"></a><a name="size"></a> サイズ

```cpp
size_t Size() const;
```

### <a name="return-value"></a>戻り値

イベント グループのサイズ。

::: moniker-end
