---
title: CComDynamicUnkArray クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::Add
- ATLCOM/ATL::CComDynamicUnkArray::begin
- ATLCOM/ATL::CComDynamicUnkArray::clear
- ATLCOM/ATL::CComDynamicUnkArray::end
- ATLCOM/ATL::CComDynamicUnkArray::GetAt
- ATLCOM/ATL::CComDynamicUnkArray::GetCookie
- ATLCOM/ATL::CComDynamicUnkArray::GetSize
- ATLCOM/ATL::CComDynamicUnkArray::GetUnknown
- ATLCOM/ATL::CComDynamicUnkArray::Remove
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], managing
- CComDynamicUnkArray class
ms.assetid: 202470d7-9a1b-498f-b96d-659d681acd65
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9c3384c2c8ce03132e6525f175b9d34339b7aa26
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363924"
---
# <a name="ccomdynamicunkarray-class"></a>CComDynamicUnkArray クラス
このクラスの配列に格納**IUnknown**ポインター。  
  
## <a name="syntax"></a>構文  
  
```
class CComDynamicUnkArray
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComDynamicUnkArray::CComDynamicUnkArray](#ccomdynamicunkarray)|コンストラクターです。 コレクションの値を初期化**NULL**とコレクションのサイズを 0 にします。|  
|[CComDynamicUnkArray:: ~ CComDynamicUnkArray](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComDynamicUnkArray::Add](#add)|追加するには、このメソッドを呼び出す、`IUnknown`配列へのポインター。|  
|[CComDynamicUnkArray::begin](#begin)|最初のポインターを返します`IUnknown`コレクション内のポインター。|  
|[CComDynamicUnkArray::clear](#clear)|配列を空にします。|  
|[CComDynamicUnkArray::end](#end)|過去の最後の 1 つのポインターを返します**IUnknown**コレクション内のポインター。|  
|[CComDynamicUnkArray::GetAt](#getat)|指定したインデックス位置にある要素を取得します。|  
|[CComDynamicUnkArray::GetCookie](#getcookie)|関連付けられているクッキーを取得するには、このメソッドを呼び出して、指定された**IUnknown**ポインター。|  
|[CComDynamicUnkArray::GetSize](#getsize)|配列の長さを返します。|  
|[CComDynamicUnkArray::GetUnknown](#getunknown)|取得するには、このメソッドを呼び出して、 **IUnknown**指定された cookie に関連付けられたポインター。|  
|[CComDynamicUnkArray::Remove](#remove)|削除するには、このメソッドを呼び出す、 **IUnknown**配列からポインター。|  
  
## <a name="remarks"></a>コメント  
 **CComDynamicUnkArray**の動的に割り当てられた配列を保持**IUnknown**ポインター、接続のインターフェイスが各をポイントします。 **CComDynamicUnkArray**をパラメーターとして使用できる、 [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)テンプレート クラス。  
  
 **CComDynamicUnkArray**メソッド[開始](#begin)と[終了](#end)(たとえば、イベントが発生したときに) すべてのコネクション ポイントをループするために使用できます。  
  
 参照してください[オブジェクトへの接続ポイントの追加](../../atl/adding-connection-points-to-an-object.md)詳細については接続の作成を自動化することでプロキシをポイントします。  
  
> [!NOTE]
> **注**クラス**CComDynamicUnkArray**によって使用される、**クラスの追加**に接続ポイントが存在するコントロールの作成時にウィザード。 接続ポイントの数を手動で指定する場合は、変更からの参照を**CComDynamicUnkArray**に`CComUnkArray<` *n* `>`ここで、 *n*必要な接続ポイントの数です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="add"></a>  CComDynamicUnkArray::Add  
 追加するには、このメソッドを呼び出す、 **IUnknown**配列へのポインター。  
  
```
DWORD Add(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnk*  
 **IUnknown**配列に追加へのポインター。  
  
### <a name="return-value"></a>戻り値  
 新しく追加されたポインターに関連付けられた cookie を返します。  
  
##  <a name="begin"></a>  CComDynamicUnkArray::begin  
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
  
##  <a name="clear"></a>  CComDynamicUnkArray::clear  
 配列を空にします。  
  
```
void clear();
```  
  
##  <a name="ccomdynamicunkarray"></a>  CComDynamicUnkArray::CComDynamicUnkArray  
 コンストラクターです。  
  
```
CComDynamicUnkArray();
```  
  
### <a name="remarks"></a>コメント  
 コレクションのサイズを 0 に設定し、値を初期化**NULL**です。 デストラクターは、必要な場合に、コレクションを解放します。  
  
##  <a name="dtor"></a>  CComDynamicUnkArray:: ~ CComDynamicUnkArray  
 デストラクターです。  
  
```
~CComDynamicUnkArray();
```  
  
### <a name="remarks"></a>コメント  
 クラスのコンス トラクターによって割り当てられたリソースを解放します。  
  
##  <a name="end"></a>  CComDynamicUnkArray::end  
 過去の最後の 1 つのポインターを返します**IUnknown**コレクション内のポインター。  
  
```
IUnknown**
    end();
```     
  
### <a name="return-value"></a>戻り値  
 ポインター、 **IUnknown**インターフェイス ポインター。  
  
##  <a name="getat"></a>  CComDynamicUnkArray::GetAt  
 指定したインデックス位置にある要素を取得します。  
  
```
IUnknown* GetAt(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 取得する要素のインデックス。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)インターフェイスです。  
  
##  <a name="getcookie"></a>  CComDynamicUnkArray::GetCookie  
 関連付けられているクッキーを取得するには、このメソッドを呼び出して、指定された**IUnknown**ポインター。  
  
```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppFind`  
 **IUnknown**ポインターが関連付けられているクッキーが必要です。  
  
### <a name="return-value"></a>戻り値  
 関連付けられた cookie を返し、 **IUnknown**ポインター、または一致する場合は 0 を**IUnknown**ポインターが見つかりました。  
  
### <a name="remarks"></a>コメント  
 同じ 2 つ以上のインスタンスがあるかどうかは**IUnknown**ポインター、この関数は、1 つ目の cookie を返します。  
  
##  <a name="getsize"></a>  CComDynamicUnkArray::GetSize  
 配列の長さを返します。  
  
```
int GetSize() const;
```  
  
### <a name="return-value"></a>戻り値  
 配列の長さ。  
  
##  <a name="getunknown"></a>  CComDynamicUnkArray::GetUnknown  
 取得するには、このメソッドを呼び出して、 **IUnknown**指定された cookie に関連付けられたポインター。  
  
```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwCookie`  
 対象の cookie、関連付けられている**IUnknown**ポインターが必要です。  
  
### <a name="return-value"></a>戻り値  
 返します、 **IUnknown**ポインター、または一致する cookie が見つからない場合は NULL です。  
  
##  <a name="remove"></a>  CComDynamicUnkArray::Remove  
 削除するには、このメソッドを呼び出す、 **IUnknown**配列からポインター。  
  
```
BOOL Remove(DWORD dwCookie);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwCookie`  
 Cookie の参照、 **IUnknown**配列から削除するへのポインター。  
  
### <a name="return-value"></a>戻り値  
 ポインターが削除されたかどうかは TRUE を返しますそれ以外の場合は FALSE。  
  
## <a name="see-also"></a>関連項目  
 [CComUnkArray クラス](../../atl/reference/ccomunkarray-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
