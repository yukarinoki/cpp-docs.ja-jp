---
title: EventSource クラス |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-windows
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 08347b4ccfa44d8645acc2bd5e96775bab4e7740
ms.sourcegitcommit: 87d317ac62620c606464d860aaa9e375a91f4c99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2018
ms.locfileid: "45601497"
---
# <a name="eventsource-class"></a>EventSource クラス

非アジャイルのイベントを表します。 `EventSource` メンバー関数は、イベント ハンドラーの追加、削除、および呼び出しを実行します。 アジャイルのイベントを使用して[AgileEventSource](agileeventsource-class.md)します。

## <a name="syntax"></a>構文

```cpp
template<typename TDelegateInterface>
class EventSource;
```

### <a name="parameters"></a>パラメーター

*TDelegateInterface*  
イベント ハンドラーを表すデリゲートのインターフェイスです。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

| 名前                                     | 説明                                            |
| ---------------------------------------- | ------------------------------------------------------ |
| [Eventsource::eventsource](#eventsource) | `EventSource` クラスの新しいインスタンスを初期化します。 |

### <a name="public-methods"></a>パブリック メソッド

| 名前                                 | 説明                                                                                                                                                      |
| ------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Eventsource::add](#add)             | 現在のイベント ハンドラーのセットを指定したデリゲート インターフェイスによって表されるイベント ハンドラーを追加します。`EventSource`オブジェクト。                     |
| [Eventsource::getsize](#getsize)     | 現在関連付けられているイベント ハンドラーの数を取得`EventSource`オブジェクト。                                                                         |
| [Eventsource::invokeall](#invokeall) | 現在関連付けられている各イベント ハンドラーを呼び出す`EventSource`オブジェクトの指定された引数の型と引数を使用します。                                      |
| [Eventsource::remove](#remove)       | 現在関連付けられているイベント ハンドラーのセットから、指定されたイベント登録トークンによって表されるイベント ハンドラーを削除します。`EventSource`オブジェクト。 |

### <a name="protected-data-members"></a>プロテクト データ メンバー

| 名前                                                    | 説明                                                                                                                       |
| ------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| [Eventsource::addremovelock _](#addremovelock)           | アクセスを同期、 [targets _](#targets)配列を追加するときに、削除、またはイベント ハンドラーを呼び出します。                          |
| [Eventsource::targets _](#targets)                       | 1 つまたは複数のイベント ハンドラーの配列。                                                                                           |
| [Eventsource::targetspointerlock _](#targetspointerlock) | この eventsource イベントのハンドラーが追加されている場合でも、削除、または呼び出される内部データ メンバーへのアクセスを同期します。 |

## <a name="inheritance-hierarchy"></a>継承階層

`EventSource`

## <a name="requirements"></a>要件

**ヘッダー:** event.h

**名前空間:** Microsoft::WRL

## <a name="add"></a>Eventsource::add

現在のイベント ハンドラーのセットを指定したデリゲート インターフェイスによって表されるイベント ハンドラーを追加します。`EventSource`オブジェクト。

```cpp
HRESULT Add(
   _In_ TDelegateInterface* delegateInterface,
   _Out_ EventRegistrationToken* token
);
```

### <a name="parameters"></a>パラメーター

*delegateInterface*  
イベント ハンドラーを表すデリゲート オブジェクトのインターフェイスです。

*token*  
この操作の完了時、イベントを表すハンドルです。 パラメーターとしてこのトークンを使用して、 [Remove()](#remove)メソッドをイベント ハンドラーを破棄します。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="addremovelock"></a>Eventsource::addremovelock _

アクセスを同期、 [targets _](#targets)配列を追加するときに、削除、またはイベント ハンドラーを呼び出します。

```cpp
Wrappers::SRWLock addRemoveLock_;
```

## <a name="eventsource"></a>Eventsource::eventsource

`EventSource` クラスの新しいインスタンスを初期化します。

```cpp
EventSource();
```

## <a name="getsize"></a>Eventsource::getsize

現在関連付けられているイベント ハンドラーの数を取得`EventSource`オブジェクト。

```cpp
size_t GetSize() const;
```

### <a name="return-value"></a>戻り値

内のイベント ハンドラーの数[targets _](#targets)します。

## <a name="invokeall"></a>Eventsource::invokeall

現在関連付けられている各イベント ハンドラーを呼び出す`EventSource`オブジェクトの指定された引数の型と引数を使用します。

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

*T0*  
0 番目のイベント ハンドラーの引数の型。

*T1*  
最初のイベント ハンドラーの引数の型。

*T2*  
2 番目のイベント ハンドラーの引数の型。

*T3*  
3 番目のイベント ハンドラーの引数の型。

*T4*  
4 番目のイベント ハンドラーの引数の型。

*T5*  
5 番目のイベント ハンドラーの引数の型。

*T6*  
6 番目のイベント ハンドラーの引数の型。

*T7*  
7 番目のイベント ハンドラーの引数の型。

*T8*  
8 番目のイベント ハンドラーの引数の型。

*T9*  
9 番目のイベント ハンドラーの引数の型。

*arg0*  
0 番目のイベント ハンドラーの引数。

*arg1*  
最初のイベント ハンドラーの引数。

*Arg2*  
2 番目のイベント ハンドラーの引数。

*arg3…*  
3 番目のイベント ハンドラーの引数。

*arg4*  
4 番目のイベント ハンドラーの引数。

*arg5*  
5 番目のイベント ハンドラーの引数。

*arg6*  
6 番目のイベント ハンドラーの引数。

*arg7*  
7 番目のイベント ハンドラーの引数。

*arg8*  
8 番目のイベント ハンドラーの引数。

*arg9*  
9 番目のイベント ハンドラーの引数。

## <a name="remove"></a>Eventsource::remove

現在関連付けられているイベント ハンドラーのセットから、指定されたイベント登録トークンによって表されるイベント ハンドラーを削除します。`EventSource`オブジェクト。

```cpp
HRESULT Remove(
   EventRegistrationToken token
);
```

### <a name="parameters"></a>パラメーター

*token*  
イベント ハンドラーを表すハンドル。 このトークンはイベント ハンドラーの登録時に返された、 [Add()](#add)メソッド。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

### <a name="remarks"></a>Remarks

詳細については、`EventRegistrationToken`構造体を参照してください、 **Windows::Foundation::EventRegistrationToken 構造**でトピック、 **Windows ランタイム**リファレンス ドキュメント。

## <a name="targets"></a>Eventsource::targets _

1 つまたは複数のイベント ハンドラーの配列。

```cpp
ComPtr<Details::EventTargetArray> targets_;
```

### <a name="remarks"></a>Remarks

ときに、現在で表されるイベント`EventSource`オブジェクトが、イベント ハンドラーは呼び出されます。

## <a name="targetspointerlock"></a>Eventsource::targetspointerlock _

このイベント ハンドラーの中にも、内部データ メンバーへのアクセスを同期`EventSource`の追加、削除、または呼び出されました。

```cpp
Wrappers::SRWLock targetsPointerLock_;
```
