---
title: Event クラス (WRL)
ms.date: 09/24/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Event
- corewrappers/Microsoft::WRL::Wrappers::Event::Event
- corewrappers/Microsoft::WRL::Wrappers::Event::operator=
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Event class
- Microsoft::WRL::Wrappers::Event::Event, constructor
- Microsoft::WRL::Wrappers::Event::operator= operator
ms.assetid: 55dfc9fc-62d4-4bb2-9d85-5b6dd88569e8
ms.openlocfilehash: 85b4c2d1f1a27e90a65e47aa749e079f4aa08739
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371520"
---
# <a name="event-class-wrl"></a>Event クラス (WRL)

イベントを表します。

## <a name="syntax"></a>構文

```cpp
class Event : public HandleT<HandleTraits::EventTraits>;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                   | 説明
---------------------- | ------------------------------------------------
[イベント::イベント](#event) | `Event` クラスの新しいインスタンスを初期化します。

### <a name="public-operators"></a>パブリック演算子

名前                                 | 説明
------------------------------------ | ------------------------------------------------------------------------
[イベント::演算子=](#operator-assign) | 指定した`Event`参照を現在`Event`のインスタンスに割り当てます。

## <a name="inheritance-hierarchy"></a>継承階層

`HandleT`

`Event`

## <a name="requirements"></a>必要条件

**ヘッダー:** コアラッパー.h

**名前空間:** マイクロソフト::WRL::ラッパー

## <a name="eventevent"></a><a name="event"></a>イベント::イベント

`Event` クラスの新しいインスタンスを初期化します。

```cpp
explicit Event(
   HANDLE h = HandleT::Traits::GetInvalidValue()
);
WRL_NOTHROW Event(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>パラメーター

*H*<br/>
イベントに対するハンドル。 既定では、 *h*は`nullptr`に初期化されます。

## <a name="eventoperator"></a><a name="operator-assign"></a>イベント::演算子=

指定した`Event`参照を現在`Event`のインスタンスに割り当てます。

```cpp
WRL_NOTHROW Event& operator=(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>パラメーター

*H*<br/>
`Event`インスタンスへの右辺値参照。

### <a name="return-value"></a>戻り値

現在`Event`のインスタンスへのポインター。
