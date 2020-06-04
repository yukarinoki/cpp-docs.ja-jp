---
title: EventSource クラス
ms.date: 09/12/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource
- event/Microsoft::WRL::EventSource::Add
- event/Microsoft::WRL::EventSource::addRemoveLock_
- event/Microsoft::WRL::EventSource::EventSource
- event/Microsoft::WRL::EventSource::GetSize
- event/Microsoft::WRL::EventSource::InvokeAll
- event/Microsoft::WRL::EventSource::Remove
- event/Microsoft::WRL::EventSource::targets_
- event/Microsoft::WRL::EventSource::targetsPointerLock_
helpviewer_keywords:
- Microsoft::WRL::EventSource class
- Microsoft::WRL::EventSource::Add method
- Microsoft::WRL::EventSource::addRemoveLock_ data member
- Microsoft::WRL::EventSource::EventSource, constructor
- Microsoft::WRL::EventSource::GetSize method
- Microsoft::WRL::EventSource::InvokeAll method
- Microsoft::WRL::EventSource::Remove method
- Microsoft::WRL::EventSource::targets_ data member
- Microsoft::WRL::EventSource::targetsPointerLock_ data member
ms.assetid: 91f1c072-6af4-44e6-b6d8-ac6d0c688dde
ms.openlocfilehash: bb9151e55d133e3e5d8bf10baeb8448101ad6ce0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371534"
---
# <a name="eventsource-class"></a>EventSource クラス

非アジャイル イベントを表します。 `EventSource` メンバー関数は、イベント ハンドラーの追加、削除、および呼び出しを実行します。 アジャイル イベントの場合は、[アジャイル イベントソース を](agileeventsource-class.md)使用します。

## <a name="syntax"></a>構文

```cpp
template<typename TDelegateInterface>
class EventSource;
```

### <a name="parameters"></a>パラメーター

*インターフェイス*<br/>
イベント ハンドラーを表すデリゲートへのインターフェイス。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

| 名前                                     | 説明                                            |
| ---------------------------------------- | ------------------------------------------------------ |
| [イベントソース::イベントソース](#eventsource) | `EventSource` クラスの新しいインスタンスを初期化します。 |

### <a name="public-methods"></a>パブリック メソッド

| 名前                                 | 説明                                                                                                                                                      |
| ------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [イベントソース::追加](#add)             | 指定したデリゲート インターフェイスによって表されるイベント ハンドラーを、現在`EventSource`のオブジェクトのイベント ハンドラーのセットに追加します。                     |
| [イベントソース::ゲットサイズ](#getsize)     | 現在`EventSource`のオブジェクトに関連付けられているイベント ハンドラーの数を取得します。                                                                         |
| [イベントソース::すべての呼び出し](#invokeall) | 指定した引数の型と引数を`EventSource`使用して、現在のオブジェクトに関連付けられた各イベント ハンドラーを呼び出します。                                      |
| [イベントソース::削除](#remove)       | 現在`EventSource`のオブジェクトに関連付けられているイベント ハンドラーのセットから、指定したイベント登録トークンによって表されるイベント ハンドラーを削除します。 |

### <a name="protected-data-members"></a>プロテクト データ メンバー

| 名前                                                    | 説明                                                                                                                       |
| ------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| [イベントソース::addRemoveLock_](#addremovelock)           | イベント ハンドラーの追加、削除、または呼び出し時に[、targets_](#targets)配列へのアクセスを同期します。                          |
| [イベントソース::targets_](#targets)                       | 1 つ以上のイベント ハンドラーの配列。                                                                                           |
| [イベントソース::targetsPointerLock_](#targetspointerlock) | この EventSource のイベント ハンドラーが追加、削除、または呼び出されている間も、内部データ メンバーへのアクセスを同期します。 |

## <a name="inheritance-hierarchy"></a>継承階層

`EventSource`

## <a name="requirements"></a>必要条件

**ヘッダー:** イベント.h

**名前空間:** Microsoft::WRL

## <a name="eventsourceadd"></a><a name="add"></a>イベントソース::追加

指定したデリゲート インターフェイスによって表されるイベント ハンドラーを、現在`EventSource`のオブジェクトのイベント ハンドラーのセットに追加します。

```cpp
HRESULT Add(
   _In_ TDelegateInterface* delegateInterface,
   _Out_ EventRegistrationToken* token
);
```

### <a name="parameters"></a>パラメーター

*インターフェイスをデリゲートします。*<br/>
イベント ハンドラーを表すデリゲート オブジェクトへのインターフェイス。

*トークン*<br/>
この操作が完了すると、イベントを表すハンドル。 このトークンを[Remove()](#remove)メソッドのパラメーターとして使用して、イベント ハンドラーを破棄します。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="eventsourceaddremovelock_"></a><a name="addremovelock"></a>イベントソース::addRemoveLock_

イベント ハンドラーの追加、削除、または呼び出し時に[、targets_](#targets)配列へのアクセスを同期します。

```cpp
Wrappers::SRWLock addRemoveLock_;
```

## <a name="eventsourceeventsource"></a><a name="eventsource"></a>イベントソース::イベントソース

`EventSource` クラスの新しいインスタンスを初期化します。

```cpp
EventSource();
```

## <a name="eventsourcegetsize"></a><a name="getsize"></a>イベントソース::ゲットサイズ

現在`EventSource`のオブジェクトに関連付けられているイベント ハンドラーの数を取得します。

```cpp
size_t GetSize() const;
```

### <a name="return-value"></a>戻り値

[targets_](#targets)内のイベント ハンドラの数。

## <a name="eventsourceinvokeall"></a><a name="invokeall"></a>イベントソース::すべての呼び出し

指定した引数の型と引数を`EventSource`使用して、現在のオブジェクトに関連付けられた各イベント ハンドラーを呼び出します。

```cpp
void InvokeAll();
template <
   typename T0
>
void InvokeAll(
   T0arg0
);
template <
   typename T0,
   typename T1
>
void InvokeAll(
   T0arg0,
   T1arg1
);
template <
   typename T0,
   typename T1,
   typename T2
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6,
   typename T7
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6,
   T7arg7
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6,
   typename T7,
   typename T8
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6,
   T7arg7,
   T8arg8
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6,
   typename T7,
   typename T8,
   typename T9
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6,
   T7arg7,
   T8arg8,
   T9arg9
);
```

### <a name="parameters"></a>パラメーター

*T0*<br/>
0 番目のイベント ハンドラー引数の型。

*T1*<br/>
最初のイベント ハンドラー引数の型。

*T2*<br/>
2 番目のイベント ハンドラー引数の型。

*T3*<br/>
3 番目のイベント ハンドラー引数の型。

*T4*<br/>
4 番目のイベント ハンドラー引数の型。

*T5*<br/>
5 番目のイベント ハンドラー引数の型。

*T6*<br/>
6 番目のイベント ハンドラー引数の型。

*T7*<br/>
7 番目のイベント ハンドラー引数の型。

*T8*<br/>
8 番目のイベント ハンドラー引数の型。

*T9*<br/>
9 番目のイベント ハンドラー引数の型。

*arg0*<br/>
0 番目のイベント ハンドラー引数。

*arg1*<br/>
最初のイベント ハンドラー引数。

*arg2*<br/>
2 番目のイベント ハンドラー引数。

*arg3*<br/>
3 番目のイベント ハンドラー引数。

*arg4*<br/>
4 番目のイベント ハンドラー引数。

*arg5*<br/>
5 番目のイベント ハンドラー引数。

*arg6*<br/>
6 番目のイベント ハンドラー引数。

*arg7*<br/>
7 番目のイベント ハンドラー引数。

*arg8*<br/>
8 番目のイベント ハンドラー引数。

*arg9*<br/>
9 番目のイベント ハンドラー引数。

## <a name="eventsourceremove"></a><a name="remove"></a>イベントソース::削除

現在`EventSource`のオブジェクトに関連付けられているイベント ハンドラーのセットから、指定したイベント登録トークンによって表されるイベント ハンドラーを削除します。

```cpp
HRESULT Remove(
   EventRegistrationToken token
);
```

### <a name="parameters"></a>パラメーター

*トークン*<br/>
イベント ハンドラーを表すハンドル。 このトークンは、イベント ハンドラーが[Add()](#add)メソッドによって登録されたときに返されました。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

### <a name="remarks"></a>解説

構造の`EventRegistrationToken`詳細については、Windows ランタイムのリファレンス ドキュメントのトピック **「Windows::Foundation::イベント登録トークン構造**」を参照してください。 **Windows Runtime**

## <a name="eventsourcetargets_"></a><a name="targets"></a>イベントソース::targets_

1 つ以上のイベント ハンドラーの配列。

```cpp
ComPtr<Details::EventTargetArray> targets_;
```

### <a name="remarks"></a>解説

現在`EventSource`のオブジェクトによって表されるイベントが発生すると、イベント ハンドラーが呼び出されます。

## <a name="eventsourcetargetspointerlock_"></a><a name="targetspointerlock"></a>イベントソース::targetsPointerLock_

イベント`EventSource`ハンドラが追加、削除、または呼び出されている間も、内部データ メンバーへのアクセスを同期します。

```cpp
Wrappers::SRWLock targetsPointerLock_;
```
