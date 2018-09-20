---
title: DeferrableEventArgs クラス |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::DeferrableEventArgs
- event/Microsoft::WRL::DeferrableEventArgs::GetDeferral
- event/Microsoft::WRL::DeferrableEventArgs::InvokeAllFinished
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::DeferrableEventArgs class
- Microsoft::WRL::DeferrableEventArgs::GetDeferral method
- Microsoft::WRL::DeferrableEventArgs::InvokeAllFinished method
ms.assetid: ece89267-7b72-40e1-8185-550c865b070a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 082cae10bbd01c4c46fcfaa84bfd94ba6178bc1a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401785"
---
# <a name="deferrableeventargs-class"></a>DeferrableEventArgs クラス

遅延のイベント引数の型に使用されるテンプレート クラス。

## <a name="syntax"></a>構文

```cpp
template <
typename TEventArgsInterface,
typename TEventArgsClass
>
class DeferrableEventArgs : public TEventArgsInterface
```

### <a name="parameters"></a>パラメーター

*TEventArgsInterface*<br/>
遅延イベントの引数を宣言するインターフェイスの型。

*TEventArgsClass*<br/>
実装するクラス*TEventArgsInterface*します。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

名前                                                         | 説明
------------------------------------------------------------ | -----------------------------------------------------------------------------------------------------------------------------
[Deferrableeventargs::getdeferral](#getdeferral)             | 参照を取得、[遅延](http://go.microsoft.com/fwlink/p/?linkid=526520)遅延イベントを表すオブジェクト。
[Deferrableeventargs::invokeallfinished](#invokeallfinished) | 遅延イベントを処理するすべての処理が完了したことを示すために呼び出されます。

## <a name="remarks"></a>Remarks

このクラスのインスタンスは、遅延イベントのイベント ハンドラーに渡されます。 テンプレート パラメーターは、遅延イベントの特定の種類のイベント引数の詳細を定義するインターフェイスと、そのインターフェイスを実装するクラスを表します。

クラスは遅延イベントのイベント ハンドラーの最初の引数として表示されます。 呼び出すことができます、 [GetDeferral](#getdeferral)を取得するメソッド、[遅延](http://go.microsoft.com/fwlink/p/?linkid=526520)遅延イベントに関するすべての情報を表示するオブジェクト。 イベント処理を完了した後、遅延オブジェクトで Complete を呼び出す必要があります。 呼び出す必要がありますし、 [InvokeAllFinished](#invokeallfinished)イベント ハンドラー メソッドの末尾には、保証すべて遅延イベントの完了が正しく伝達されます。

## <a name="requirements"></a>要件

**ヘッダー:** event.h

**名前空間:** Microsoft::WRL

## <a name="getdeferral"></a>Deferrableeventargs::getdeferral

参照を取得、[遅延](http://go.microsoft.com/fwlink/p/?linkid=526520)遅延イベントを表すオブジェクト。

```cpp
HRESULT GetDeferral([out, retval] Windows::Foundation::IDeferral** result)  
```

### <a name="parameters"></a>パラメーター

*結果*<br/>
参照するポインター、[遅延](http://go.microsoft.com/fwlink/p/?linkid=526520)呼び出しの完了時のオブジェクトします。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="invokeallfinished"></a>Deferrableeventargs::invokeallfinished

遅延イベントを処理するすべての処理が完了したことを示すために呼び出されます。
  
```cpp
void InvokeAllFinished()  
```
  
### <a name="remarks"></a>Remarks

イベント ソース呼び出しの後にこのメソッドを呼び出す必要があります[InvokeAll](../windows/eventsource-invokeall-method.md)します。 このメソッドを呼び出すことで、さらに遅延が取られることを回避し、遅延が取られなかった場合は、完了ハンドラーの実行を強制します。
