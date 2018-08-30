---
title: CComGITPtr クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComGITPtr
- ATLBASE/ATL::CComGITPtr
- ATLBASE/ATL::CComGITPtr::CComGITPtr
- ATLBASE/ATL::CComGITPtr::Attach
- ATLBASE/ATL::CComGITPtr::CopyTo
- ATLBASE/ATL::CComGITPtr::Detach
- ATLBASE/ATL::CComGITPtr::GetCookie
- ATLBASE/ATL::CComGITPtr::Revoke
- ATLBASE/ATL::CComGITPtr::m_dwCookie
dev_langs:
- C++
helpviewer_keywords:
- CComGITPtr class
ms.assetid: af895acb-525a-4555-bb67-b241b7df515b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a45866226f06b20d0805b7c4e294ff6d2d65506e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43197921"
---
# <a name="ccomgitptr-class"></a>CComGITPtr クラス
このクラスは、インターフェイス ポインターを処理するためのメソッドおよびグローバル インターフェイス テーブル (GIT) を提供します。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
class CComGITPtr
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 GIT で格納されるインターフェイス ポインターの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComGITPtr::CComGITPtr](#ccomgitptr)|コンストラクターです。|  
|[CComGITPtr:: ~ CComGITPtr](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComGITPtr::Attach](#attach)|グローバル インターフェイス テーブル (GIT) のインターフェイス ポインターを登録するには、このメソッドを呼び出します。|  
|[CComGITPtr::CopyTo](#copyto)|インターフェイスをグローバル インターフェイス テーブル (GIT) から渡されたポインターにコピーするには、このメソッドを呼び出します。|  
|[CComGITPtr::Detach](#detach)|インターフェイスの関連付けを解除するには、このメソッドを呼び出して、`CComGITPtr`オブジェクト。|  
|[CComGITPtr::GetCookie](#getcookie)|このメソッドから cookie を返すを呼び出して、`CComGITPtr`オブジェクト。|  
|[CComGITPtr::Revoke](#revoke)|グローバル インターフェイス テーブル (GIT) から、インターフェイスを削除するには、このメソッドを呼び出します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CComGITPtr::operator DWORD](#operator_dword)|Cookie を返します、`CComGITPtr`オブジェクト。|  
|[CComGITPtr::operator =](#operator_eq)|代入演算子。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComGITPtr::m_dwCookie](#m_dwcookie)|クッキー。|  
  
## <a name="remarks"></a>Remarks  
 フリー スレッド マーシャラーを集約し、その他のオブジェクトから取得したインターフェイス ポインターを使用する必要があるオブジェクトは、インターフェイスが正しくマーシャ リングすることを確認する追加の手順を実行する必要があります。 通常これは、GIT でインターフェイス ポインターを格納して、使用されるたびに、GIT からポインターを取得する必要があります。 クラスは、 `CComGITPtr` GIT に格納されているインターフェイス ポインターを使用するために提供されます。  
  
> [!NOTE]
>  グローバル インターフェイス テーブルの機能は、DCOM バージョン 1.1 で Windows 95 以降、Windows 98、Windows NT 4.0 Service Pack 3 以降、および Windows 2000 にできるだけです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="attach"></a>  CComGITPtr::Attach  
 グローバル インターフェイス テーブル (GIT) のインターフェイス ポインターを登録するには、このメソッドを呼び出します。  
  
```
HRESULT Attach(T* p) throw();

HRESULT Attach(DWORD dwCookie) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *p*  
 GIT に追加するインターフェイス ポインター。  
  
 *dwCookie*  
 インターフェイス ポインターを識別するために使用されるクッキー。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>Remarks  
 デバッグ ビルドでは、GIT が有効でない場合、またはクッキーが null の場合に、アサーション エラーが発生します。  
  
##  <a name="ccomgitptr"></a>  CComGITPtr::CComGITPtr  
 コンストラクターです。  
  
```
CComGITPtr() throw();
CComGITPtr(T* p);
CComGITPtr(const CComGITPtr& git);
explicit CComGITPtr(DWORD dwCookie) throw();
CComGITPtr(CComGITPtr&& rv);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*p*  
 グローバル インターフェイス テーブル (GIT) に格納されるインターフェイス ポインター。  
  
 [in]*git*  
 既存への参照を`CComGITPtr`オブジェクト。  
  
 [in]*dwCookie*  
 インターフェイス ポインターを識別するために使用されるクッキー。  
  
 [in]*rv*  
 ソース`CComGITPtr`からデータを移動するオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 新たに作成`CComGITPtr`オブジェクト、必要に応じて、既存を使用して`CComGITPtr`オブジェクト。  
  
 コンス トラクターの利用*rv*移動コンス トラクターです。 元のデータを移動*rv*、し*rv*がオフになっています。  
  
##  <a name="dtor"></a>  CComGITPtr:: ~ CComGITPtr  
 デストラクターです。  
  
```
~CComGITPtr() throw();
```  
  
### <a name="remarks"></a>Remarks  
 グローバル インターフェイス テーブル (GIT) から、インターフェイスを削除します。 を使用して[CComGITPtr::Revoke](#revoke)します。  
  
##  <a name="copyto"></a>  CComGITPtr::CopyTo  
 インターフェイスをグローバル インターフェイス テーブル (GIT) から渡されたポインターにコピーするには、このメソッドを呼び出します。  
  
```
HRESULT CopyTo(T** pp) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *pp*  
 これは、インターフェイスを受信するポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>Remarks  
 GIT からのインターフェイスは、渡されたポインターにコピーされます。 ポインターは、必要でなくなったとき、呼び出し元がリリースする必要があります。  
  
##  <a name="detach"></a>  CComGITPtr::Detach  
 インターフェイスの関連付けを解除するには、このメソッドを呼び出して、`CComGITPtr`オブジェクト。  
  
```
DWORD Detach() throw();
```  
  
### <a name="return-value"></a>戻り値  
 Cookie を返します、`CComGITPtr`オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 呼び出し元が、GIT からのインターフェイスを削除するまでを使用して[CComGITPtr::Revoke](#revoke)します。  
  
##  <a name="getcookie"></a>  CComGITPtr::GetCookie  
 このメソッドから cookie を返すを呼び出して、`CComGITPtr`オブジェクト。  
  
```
DWORD GetCookie() const;
```  
  
### <a name="return-value"></a>戻り値  
 Cookie を返します。  
  
### <a name="remarks"></a>Remarks  
 Cookie は、インターフェイスとその場所を識別するために使用される変数です。  
  
##  <a name="m_dwcookie"></a>  CComGITPtr::m_dwCookie  
 クッキー。  
  
```
DWORD m_dwCookie;
```  
  
### <a name="remarks"></a>Remarks  
 Cookie は、インターフェイスとその場所を識別するために使用されるメンバー変数です。  
  
##  <a name="operator_eq"></a>  CComGITPtr::operator =  
 代入演算子です。  
  
```
CComGITPtr& operator= (T* p);
CComGITPtr& operator= (const CComGITPtr& git);
CComGITPtr& operator= (DWORD dwCookie);
CComGITPtr& operator= (CComGITPtr&& rv);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*p*  
 インターフェイスへのポインター。  
  
 [in]*git*  
 `CComGITPtr` オブジェクトへの参照。  
  
 [in]*dwCookie*  
 インターフェイス ポインターを識別するために使用されるクッキー。  
  
 [in]*rv*  
 `CComGITPtr`からデータを移動します。  
  
### <a name="return-value"></a>戻り値  
 更新された返します`CComGITPtr`オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 新しい値を割り当てます、`CComGITPtr`オブジェクト、既存のオブジェクトまたはグローバル インターフェイス テーブルへの参照。  
  
##  <a name="operator_dword"></a>  CComGITPtr::operator DWORD  
 関連付けられているクッキーを返します、`CComGITPtr`オブジェクト。  
  
```  
operator DWORD() const;
```  
  
### <a name="remarks"></a>Remarks  
 Cookie は、インターフェイスとその場所を識別するために使用される変数です。  
  
##  <a name="revoke"></a>  CComGITPtr::Revoke  
 グローバル インターフェイス テーブル (GIT) から現在のインターフェイスを削除するには、このメソッドを呼び出します。  
  
```
HRESULT Revoke() throw();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>Remarks  
 GIT から、インターフェイスを削除します。  
  
## <a name="see-also"></a>関連項目  
 [フリー スレッド マーシャラー](../../atl/atl-and-the-free-threaded-marshaler.md)   
 [アパートメント間でインターフェイスへのアクセス](/windows/desktop/com/accessing-interfaces-across-apartments)   
 [グローバル インターフェイス テーブルを使用する場合](/windows/desktop/com/when-to-use-the-global-interface-table)   
 [クラスの概要](../../atl/atl-class-overview.md)
