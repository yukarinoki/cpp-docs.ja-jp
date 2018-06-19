---
title: CComUnkArray クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComUnkArray
- ATLCOM/ATL::CComUnkArray
- ATLCOM/ATL::CComUnkArray::CComUnkArray
- ATLCOM/ATL::CComUnkArray::Add
- ATLCOM/ATL::CComUnkArray::begin
- ATLCOM/ATL::CComUnkArray::end
- ATLCOM/ATL::CComUnkArray::GetCookie
- ATLCOM/ATL::CComUnkArray::GetUnknown
- ATLCOM/ATL::CComUnkArray::Remove
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], managing
- CComUnkArray class
ms.assetid: 5fd4b378-a7b5-4cc1-8866-8ab72a73639e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0de49180052a6fdb7bde32274e032ea1dd9bfb87
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364419"
---
# <a name="ccomunkarray-class"></a>CComUnkArray クラス
このクラスは、格納**IUnknown**ポインターへのパラメーターとして使用するものでは、 [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)テンプレート クラス。  
  
## <a name="syntax"></a>構文  
  
```
template<unsigned int nMaxSize>
class CComUnkArray
```  
  
#### <a name="parameters"></a>パラメーター  
 *nMaxSize*  
 最大数**IUnknown**静的配列内に保持できるポインター。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComUnkArray::CComUnkArray](#ccomunkarray)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComUnkArray::Add](#add)|追加するには、このメソッドを呼び出す、 **IUnknown**配列へのポインター。|  
|[CComUnkArray::begin](#begin)|最初のポインターを返します**IUnknown**コレクション内のポインター。|  
|[CComUnkArray::end](#end)|過去の最後の 1 つのポインターを返します**IUnknown**コレクション内のポインター。|  
|[CComUnkArray::GetCookie](#getcookie)|関連付けられているクッキーを取得するには、このメソッドを呼び出して、指定された**IUnknown**ポインター。|  
|[CComUnkArray::GetUnknown](#getunknown)|取得するには、このメソッドを呼び出して、 **IUnknown**指定された cookie に関連付けられたポインター。|  
|[CComUnkArray::Remove](#remove)|削除するには、このメソッドを呼び出す、 **IUnknown**配列からポインター。|  
  
## <a name="remarks"></a>コメント  
 **CComUnkArray**固定数を保持している**IUnknown**ポインター、接続のインターフェイスの各ポイントします。 **CComUnkArray**をパラメーターとして使用できる、 [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)テンプレート クラス。 **CComUnkArray\<1 >** テンプレート特殊化**CComUnkArray**の 1 つの接続ポイントを最適化されています。  
  
 **CComUnkArray**メソッド[開始](#begin)と[終了](#end)(たとえば、イベントが発生したときに) すべてのコネクション ポイントをループするために使用できます。  
  
 参照してください[オブジェクトへの接続ポイントの追加](../../atl/adding-connection-points-to-an-object.md)詳細については接続の作成を自動化することでプロキシをポイントします。  
  
> [!NOTE]
> **注**クラス[CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)によって使用される、**クラスの追加**に接続ポイントが存在するコントロールの作成時にウィザード。 接続ポイントの数を手動で指定する場合は、変更からの参照を**CComDynamicUnkArray**に`CComUnkArray<` *n* `>`ここで、 *n*必要な接続ポイントの数です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="add"></a>  CComUnkArray::Add  
 追加するには、このメソッドを呼び出す、 **IUnknown**配列へのポインター。  
  
```
DWORD Add(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnk*  
 追加するには、このメソッドを呼び出す、 **IUnknown**配列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 配列は、新しいポインターを格納するのに十分な大きさがない場合は、新しく追加されたポインター、または 0 に関連付けられているクッキーを返します。  
  
##  <a name="begin"></a>  CComUnkArray::begin  
 コレクションの先頭へのポインターを返します**IUnknown**インターフェイス ポインター。  
  
```
IUnknown**
    begin();
```     
  
### <a name="return-value"></a>戻り値  
 ポインター、 **IUnknown**インターフェイス ポインター。  
  
### <a name="remarks"></a>コメント  
 コレクションには、としてローカルに格納されているインターフェイスへのポインターが含まれています。 **IUnknown**です。 それぞれをキャストする**IUnknown**インターフェイスを実際のインターフェイス型としています。 最初のインターフェイスを照会する必要はありません。  
  
 使用する前に、 **IUnknown**されていないことを確認インターフェイス、 **NULL**です。  
  
##  <a name="ccomunkarray"></a>  CComUnkArray::CComUnkArray  
 コンストラクターです。  
  
```
CComUnkArray();
```  
  
### <a name="remarks"></a>コメント  
 設定を保持するコレクション`nMaxSize` **IUnknown**ポインターへのポインターを初期化します**NULL**です。  
  
##  <a name="end"></a>  CComUnkArray::end  
 過去の最後の 1 つのポインターを返します**IUnknown**コレクション内のポインター。  
  
```
IUnknown**
    end();
```     
  
### <a name="return-value"></a>戻り値  
 ポインター、 **IUnknown**インターフェイス ポインター。  
  
### <a name="remarks"></a>コメント  
 `CComUnkArray`メソッド**開始**と**終了**イベントが発生したときに、すべての接続ポイントは、たとえば、ループを使用できます。  
  
 [!code-cpp[NVC_ATL_COM#44](../../atl/codesnippet/cpp/ccomunkarray-class_1.cpp)]  
  
##  <a name="getcookie"></a>  CComUnkArray::GetCookie  
 関連付けられているクッキーを取得するには、このメソッドを呼び出して、指定された**IUnknown**ポインター。  
  
```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppFind`  
 **IUnknown**ポインターが関連付けられているクッキーが必要です。  
  
### <a name="return-value"></a>戻り値  
 関連付けられた cookie を返し、 **IUnknown**ポインター、または一致する場合は 0 **IUnknown**ポインターが見つかりました。  
  
### <a name="remarks"></a>コメント  
 同じ 2 つ以上のインスタンスがあるかどうかは**IUnknown**ポインター、この関数は、1 つ目の cookie を返します。  
  
##  <a name="getunknown"></a>  CComUnkArray::GetUnknown  
 取得するには、このメソッドを呼び出して、 **IUnknown**指定された cookie に関連付けられたポインター。  
  
```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwCookie`  
 対象の cookie、関連付けられている**IUnknown**ポインターが必要です。  
  
### <a name="return-value"></a>戻り値  
 返します、 **IUnknown**ポインター、または一致する cookie が見つからない場合は NULL です。  
  
##  <a name="remove"></a>  CComUnkArray::Remove  
 削除するには、このメソッドを呼び出す、 **IUnknown**配列からポインター。  
  
```
BOOL Remove(DWORD dwCookie);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwCookie`  
 Cookie の参照、 **IUnknown**配列から削除するへのポインター。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**ポインターが削除された場合は**FALSE**それ以外の場合。  
  
## <a name="see-also"></a>関連項目  
 [CComDynamicUnkArray クラス](../../atl/reference/ccomdynamicunkarray-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
