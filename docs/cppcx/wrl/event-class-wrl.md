---
description: '詳細情報: イベントクラス (WRL)'
title: イベントクラス (WRL)
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
ms.openlocfilehash: e3a61a40d1160830df80a7e0650e60fbf803e3d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272826"
---
# <a name="event-class-wrl"></a>イベントクラス (WRL)

イベントを表します。

## <a name="syntax"></a>構文

```cpp
class Event : public HandleT<HandleTraits::EventTraits>;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                   | 説明
---------------------- | ------------------------------------------------
[Event:: Event](#event) | `Event` クラスの新しいインスタンスを初期化します。

### <a name="public-operators"></a>パブリック演算子

名前                                 | 説明
------------------------------------ | ------------------------------------------------------------------------
[Event:: operator =](#operator-assign) | 指定された `Event` 参照を現在のインスタンスに割り当て `Event` ます。

## <a name="inheritance-hierarchy"></a>継承階層

`HandleT`

`Event`

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers .h

**名前空間:** Microsoft:: WRL:: Wrapper

## <a name="eventevent"></a><a name="event"></a> Event:: Event

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

*h*<br/>
イベントに対するハンドル。 既定では、 *h* はに初期化され **`nullptr`** ます。

## <a name="eventoperator"></a><a name="operator-assign"></a> Event:: operator =

指定された `Event` 参照を現在のインスタンスに割り当て `Event` ます。

```cpp
WRL_NOTHROW Event& operator=(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>パラメーター

*h*<br/>
インスタンスへの右辺値参照 `Event` 。

### <a name="return-value"></a>戻り値

現在のインスタンスへのポインター `Event` 。
