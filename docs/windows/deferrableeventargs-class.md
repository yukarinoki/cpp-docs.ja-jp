---
title: DeferrableEventArgs クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: ece89267-7b72-40e1-8185-550c865b070a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8dd9452133267021effd307734b5c5cf55922720
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642303"
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
 *TEventArgsInterface*  
 遅延イベントの引数を宣言するインターフェイスの型。  
  
 *TEventArgsClass*  
 実装するクラス*TEventArgsInterface*します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[DeferrableEventArgs::GetDeferral メソッド](../windows/deferrableeventargs-getdeferral-method.md)|参照を取得、[遅延](http://go.microsoft.com/fwlink/p/?linkid=526520)遅延イベントを表すオブジェクト。|  
|[DeferrableEventArgs::InvokeAllFinished メソッド](../windows/deferrableeventargs-invokeallfinished-method.md)|遅延イベントを処理するすべての処理が完了したことを示すために呼び出されます。|  
  
## <a name="remarks"></a>Remarks  
 このクラスのインスタンスは、遅延イベントのイベント ハンドラーに渡されます。 テンプレート パラメーターは、遅延イベントの特定の種類のイベント引数の詳細を定義するインターフェイスと、そのインターフェイスを実装するクラスを表します。  
  
 クラスは遅延イベントのイベント ハンドラーの最初の引数として表示されます。 呼び出すことができます、 [GetDeferral](../windows/deferrableeventargs-getdeferral-method.md)を取得するメソッド、[遅延](http://go.microsoft.com/fwlink/p/?linkid=526520)遅延イベントに関するすべての情報を表示するオブジェクト。 イベント処理を完了した後、遅延オブジェクトで Complete を呼び出す必要があります。 呼び出す必要がありますし、 [InvokeAllFinished](../windows/deferrableeventargs-invokeallfinished-method.md)イベント ハンドラー メソッドの末尾には、保証すべて遅延イベントの完了が正しく伝達されます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** event.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)