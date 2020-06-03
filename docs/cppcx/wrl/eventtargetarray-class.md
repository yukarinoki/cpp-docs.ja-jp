---
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
ms.openlocfilehash: 9ea8800aa22a6b5cae0b3342cf337786fb53fc76
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371495"
---
# <a name="eventtargetarray-class"></a>EventTargetArray クラス

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
class EventTargetArray :
    public Microsoft::WRL::RuntimeClass<
        Microsoft::WRL::RuntimeClassFlags<ClassicCom>,
        IUnknown
    >;
```

## <a name="remarks"></a>解説

イベント ハンドラーの配列を表します。

[EventSource](eventsource-class.md)オブジェクトに関連付けられているイベント ハンドラーは、保護された`EventTargetArray`データ メンバーに格納されます。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                                           | 説明
-------------------------------------------------------------- | -----------------------------------------------------------
[イベントターゲットアレイ::イベントターゲットアレイ](#eventtargetarray)        | `EventTargetArray` クラスの新しいインスタンスを初期化します。
[イベントターゲットアレイ:~イベントターゲットアレイ](#tilde-eventtargetarray) | 現在`EventTargetArray`のクラスを初期化解除します。

### <a name="public-methods"></a>パブリック メソッド

名前                                  | 説明
------------------------------------- | ---------------------------------------------------------------------------------------
[イベントターゲットアレイ::追加テール](#addtail) | 指定したイベント ハンドラーをイベント ハンドラーの内部配列の末尾に追加します。
[イベントターゲットアレイ::開始](#begin)     | イベント ハンドラーの内部配列の最初の要素のアドレスを取得します。
[イベントターゲットアレイ::終了](#end)         | イベント ハンドラーの内部配列の最後の要素のアドレスを取得します。
[イベントターゲットアレイ::長さ](#length)   | イベント ハンドラーの内部配列内の要素の現在の数を取得します。

## <a name="inheritance-hierarchy"></a>継承階層

`EventTargetArray`

## <a name="requirements"></a>必要条件

**ヘッダー:** イベント.h

**名前空間:** マイクロソフト::WRL::Dのテール

## <a name="eventtargetarrayeventtargetarray"></a><a name="tilde-eventtargetarray"></a>イベントターゲットアレイ:~イベントターゲットアレイ

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
~EventTargetArray();
```

### <a name="remarks"></a>解説

現在`EventTargetArray`のクラスを初期化解除します。

## <a name="eventtargetarrayaddtail"></a><a name="addtail"></a>イベントターゲットアレイ::追加テール

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
void AddTail(
   _In_ IUnknown* element
);
```

### <a name="parameters"></a>パラメーター

*要素*<br/>
追加するイベント ハンドラーへのポインター。

### <a name="remarks"></a>解説

指定したイベント ハンドラーをイベント ハンドラーの内部配列の末尾に追加します。

`AddTail()`は、クラスだけが内部的に使用することを意図しています`EventSource`。

## <a name="eventtargetarraybegin"></a><a name="begin"></a>イベントターゲットアレイ::開始

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
ComPtr<IUnknown>* Begin();
```

### <a name="return-value"></a>戻り値

イベント ハンドラーの内部配列の最初の要素のアドレス。

### <a name="remarks"></a>解説

イベント ハンドラーの内部配列の最初の要素のアドレスを取得します。

## <a name="eventtargetarrayend"></a><a name="end"></a>イベントターゲットアレイ::終了

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
ComPtr<IUnknown>* End();
```

### <a name="return-value"></a>戻り値

イベント ハンドラーの内部配列の最後の要素のアドレス。

### <a name="remarks"></a>解説

イベント ハンドラーの内部配列の最後の要素のアドレスを取得します。

## <a name="eventtargetarrayeventtargetarray"></a><a name="eventtargetarray"></a>イベントターゲットアレイ::イベントターゲットアレイ

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
EventTargetArray(
   _Out_ HRESULT* hr,
   size_t items
);
```

### <a name="parameters"></a>パラメーター

*人事*<br/>
このコンストラクターの操作後、パラメーター *hr*は配列の割り当てが成功したか失敗するかを示します。 次の一覧は、 *hr*の値を示しています。

- S_OK<br/>
  操作が成功しました。

- E_OUTOFMEMORY<br/>
  メモリを配列に割り当てることができませんでした。

- S_FALSE<br/>
  パラメータ*項目*が 0 以下です。

*items*<br/>
割り当てる配列要素の数。

### <a name="remarks"></a>解説

`EventTargetArray` クラスの新しいインスタンスを初期化します。

`EventTargetArray`は、`EventSource`イベント ハンドラの配列をオブジェクトに保持するために使用されます。

## <a name="eventtargetarraylength"></a><a name="length"></a>イベントターゲットアレイ::長さ

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
size_t Length();
```

### <a name="return-value"></a>戻り値

イベント ハンドラーの内部配列内の要素の現在の数。

### <a name="remarks"></a>解説

イベント ハンドラーの内部配列内の要素の現在の数を取得します。
