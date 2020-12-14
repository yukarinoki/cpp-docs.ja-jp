---
description: '詳細情報: EventTargetArray クラス'
title: EventTargetArray クラス
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray
- event/Microsoft::WRL::Details::EventTargetArray::AddTail
- event/Microsoft::WRL::Details::EventTargetArray::Begin
- event/Microsoft::WRL::Details::EventTargetArray::End
- event/Microsoft::WRL::Details::EventTargetArray::EventTargetArray
- event/Microsoft::WRL::Details::EventTargetArray::Length
- event/Microsoft::WRL::Details::EventTargetArray::~EventTargetArray
helpviewer_keywords:
- Microsoft::WRL::Details::EventTargetArray class
- Microsoft::WRL::Details::EventTargetArray::AddTail method
- Microsoft::WRL::Details::EventTargetArray::Begin method
- Microsoft::WRL::Details::EventTargetArray::End method
- Microsoft::WRL::Details::EventTargetArray::EventTargetArray, constructor
- Microsoft::WRL::Details::EventTargetArray::Length method
- Microsoft::WRL::Details::EventTargetArray::~EventTargetArray, destructor
ms.assetid: e3cadb7c-2160-4cbb-a2f8-c28733d1e96d
ms.openlocfilehash: ac3199d2374a47e94705f8f51672bfedd0b7bf20
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198584"
---
# <a name="eventtargetarray-class"></a>EventTargetArray クラス

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
class EventTargetArray :
    public Microsoft::WRL::RuntimeClass<
        Microsoft::WRL::RuntimeClassFlags<ClassicCom>,
        IUnknown
    >;
```

## <a name="remarks"></a>解説

イベントハンドラーの配列を表します。

[EventSource](eventsource-class.md)オブジェクトに関連付けられているイベントハンドラーは、保護されたデータメンバーに格納され `EventTargetArray` ます。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                                           | 説明
-------------------------------------------------------------- | -----------------------------------------------------------
[EventTargetArray:: EventTargetArray](#eventtargetarray)        | `EventTargetArray` クラスの新しいインスタンスを初期化します。
[EventTargetArray:: ~ EventTargetArray](#tilde-eventtargetarray) | 現在のクラスを初期化解除 `EventTargetArray` します。

### <a name="public-methods"></a>パブリック メソッド

名前                                  | 説明
------------------------------------- | ---------------------------------------------------------------------------------------
[EventTargetArray:: AddTail](#addtail) | イベントハンドラーの内部配列の末尾に、指定されたイベントハンドラーを追加します。
[EventTargetArray:: Begin](#begin)     | イベントハンドラーの内部配列内の最初の要素のアドレスを取得します。
[EventTargetArray:: End](#end)         | イベントハンドラーの内部配列内の最後の要素のアドレスを取得します。
[EventTargetArray:: Length](#length)   | イベントハンドラーの内部配列内の現在の要素数を取得します。

## <a name="inheritance-hierarchy"></a>継承階層

`EventTargetArray`

## <a name="requirements"></a>要件

**ヘッダー:** イベント .h

**名前空間:** Microsoft:: WRL::D etails

## <a name="eventtargetarrayeventtargetarray"></a><a name="tilde-eventtargetarray"></a> EventTargetArray:: ~ EventTargetArray

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
~EventTargetArray();
```

### <a name="remarks"></a>解説

現在のクラスを初期化解除 `EventTargetArray` します。

## <a name="eventtargetarrayaddtail"></a><a name="addtail"></a> EventTargetArray:: AddTail

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
void AddTail(
   _In_ IUnknown* element
);
```

### <a name="parameters"></a>パラメーター

*element*<br/>
追加するイベントハンドラーへのポインター。

### <a name="remarks"></a>解説

イベントハンドラーの内部配列の末尾に、指定されたイベントハンドラーを追加します。

`AddTail()` は、クラスのみによって内部的に使用されることを意図してい `EventSource` ます。

## <a name="eventtargetarraybegin"></a><a name="begin"></a> EventTargetArray:: Begin

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
ComPtr<IUnknown>* Begin();
```

### <a name="return-value"></a>戻り値

イベントハンドラーの内部配列内の最初の要素のアドレス。

### <a name="remarks"></a>解説

イベントハンドラーの内部配列内の最初の要素のアドレスを取得します。

## <a name="eventtargetarrayend"></a><a name="end"></a> EventTargetArray:: End

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
ComPtr<IUnknown>* End();
```

### <a name="return-value"></a>戻り値

イベントハンドラーの内部配列内の最後の要素のアドレス。

### <a name="remarks"></a>解説

イベントハンドラーの内部配列内の最後の要素のアドレスを取得します。

## <a name="eventtargetarrayeventtargetarray"></a><a name="eventtargetarray"></a> EventTargetArray:: EventTargetArray

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
EventTargetArray(
   _Out_ HRESULT* hr,
   size_t items
);
```

### <a name="parameters"></a>パラメーター

*時間*<br/>
このコンストラクター操作の後、パラメーター *hr* は配列の割り当てが成功したか失敗したかを示します。 次の一覧は、 *hr* に使用できる値を示しています。

- S_OK<br/>
  操作が成功しました。

- E_OUTOFMEMORY<br/>
  配列にメモリを割り当てられませんでした。

- S_FALSE<br/>
  パラメーター *項目* が0以下です。

*items*<br/>
割り当てる配列要素の数。

### <a name="remarks"></a>解説

`EventTargetArray` クラスの新しいインスタンスを初期化します。

`EventTargetArray` は、イベントハンドラーの配列をオブジェクトに保持するために使用され `EventSource` ます。

## <a name="eventtargetarraylength"></a><a name="length"></a> EventTargetArray:: Length

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
size_t Length();
```

### <a name="return-value"></a>戻り値

イベントハンドラーの内部配列内の現在の要素の数。

### <a name="remarks"></a>解説

イベントハンドラーの内部配列内の現在の要素数を取得します。
