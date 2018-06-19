---
title: CComGITPtr クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 049873ce6ff630e8f00ea5ad5ec9b3786bd5e71b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363627"
---
# <a name="ccomgitptr-class"></a>CComGITPtr クラス
このクラスは、インターフェイス ポインターを処理するためのメソッドと、グローバル インターフェイス テーブル (GIT) を提供します。  
  
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
|[CComGITPtr::Attach](#attach)|グローバル インターフェイス テーブル (GIT) で、インターフェイス ポインターを登録するには、このメソッドを呼び出します。|  
|[CComGITPtr::CopyTo](#copyto)|インターフェイスをグローバル インターフェイス テーブル (GIT) から渡されたポインターにコピーするには、このメソッドを呼び出します。|  
|[CComGITPtr::Detach](#detach)|インターフェイスの関連付けを解除するには、このメソッドを呼び出して、`CComGITPtr`オブジェクト。|  
|[CComGITPtr::GetCookie](#getcookie)|このメソッドから cookie を返すを呼び出して、`CComGITPtr`オブジェクト。|  
|[CComGITPtr::Revoke](#revoke)|このメソッドを呼び出して、グローバル インターフェイス テーブル (GIT) からインターフェイスを削除します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CComGITPtr::operator DWORD](#operator_dword)|Cookie を返し、`CComGITPtr`オブジェクト。|  
|[CComGITPtr::operator =](#operator_eq)|代入演算子。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComGITPtr::m_dwCookie](#m_dwcookie)|クッキー。|  
  
## <a name="remarks"></a>コメント  
 フリー スレッド マーシャラーを集約し、その他のオブジェクトから取得されたインターフェイス ポインターを使用する必要があるオブジェクトは、インターフェイスが正しくマーシャ リングすることを確認する追加の手順を実行する必要があります。 通常は、GIT にインターフェイス ポインターを格納してを使用するたびに、GIT からポインターを取得します。 クラス`CComGITPtr`GIT で格納されているインターフェイス ポインターを使用するために提供されます。  
  
> [!NOTE]
>  グローバル インターフェイス テーブル機能では、Windows 95 DCOM バージョン 1.1 をし、その後、Windows 98、Windows NT 4.0 Service Pack 3 以降では、および Windows 2000 で利用できるのみです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="attach"></a>  CComGITPtr::Attach  
 グローバル インターフェイス テーブル (GIT) で、インターフェイス ポインターを登録するには、このメソッドを呼び出します。  
  
```
HRESULT Attach(T* p) throw();

HRESULT Attach(DWORD dwCookie) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 GIT を追加するインターフェイス ポインター。  
  
 `dwCookie`  
 インターフェイス ポインターの識別に使用する cookie です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 デバッグ ビルドでは、GIT が有効でない場合、または、cookie が null の場合、アサーション エラーが発生します。  
  
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
 [入力] `p`  
 グローバル インターフェイス テーブル (GIT) に格納されるインターフェイス ポインター。  
  
 [入力] `git`  
 既存への参照を`CComGITPtr`オブジェクト。  
  
 [入力] `dwCookie`  
 インターフェイス ポインターの識別に使用する cookie です。  
  
 [入力] `rv`  
 ソース`CComGITPtr`からデータを移動するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 新たに作成`CComGITPtr`オブジェクト、必要に応じて 既存を使用して`CComGITPtr`オブジェクト。  
  
 コンス トラクターを使用して`rv`移動コンス トラクターです。 ソースからデータを移動`rv`、し`rv`がオフになっています。  
  
##  <a name="dtor"></a>  CComGITPtr:: ~ CComGITPtr  
 デストラクターです。  
  
```
~CComGITPtr() throw();
```  
  
### <a name="remarks"></a>コメント  
 グローバル インターフェイス テーブル (GIT) からインターフェイスを削除を使用して[CComGITPtr::Revoke](#revoke)です。  
  
##  <a name="copyto"></a>  CComGITPtr::CopyTo  
 インターフェイスをグローバル インターフェイス テーブル (GIT) から渡されたポインターにコピーするには、このメソッドを呼び出します。  
  
```
HRESULT CopyTo(T** pp) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pp`  
 これは、インターフェイスを受信するポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 GIT からのインターフェイスは、渡されたポインターにコピーされます。 ポインターは必要なくなりましたときに、呼び出し元によって解放する必要があります。  
  
##  <a name="detach"></a>  CComGITPtr::Detach  
 インターフェイスの関連付けを解除するには、このメソッドを呼び出して、`CComGITPtr`オブジェクト。  
  
```
DWORD Detach() throw();
```  
  
### <a name="return-value"></a>戻り値  
 Cookie を返し、`CComGITPtr`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 GIT からのインターフェイスを削除する、呼び出し元の役割を使用して[CComGITPtr::Revoke](#revoke)です。  
  
##  <a name="getcookie"></a>  CComGITPtr::GetCookie  
 このメソッドから cookie を返すを呼び出して、`CComGITPtr`オブジェクト。  
  
```
DWORD GetCookie() const;
```  
  
### <a name="return-value"></a>戻り値  
 Cookie を返します。  
  
### <a name="remarks"></a>コメント  
 Cookie は、インターフェイスとその場所の識別に使用される変数です。  
  
##  <a name="m_dwcookie"></a>  CComGITPtr::m_dwCookie  
 クッキー。  
  
```
DWORD m_dwCookie;
```  
  
### <a name="remarks"></a>コメント  
 Cookie は、メンバー変数がインターフェイスとその場所を識別するためです。  
  
##  <a name="operator_eq"></a>  CComGITPtr::operator =  
 代入演算子です。  
  
```
CComGITPtr& operator= (T* p);
CComGITPtr& operator= (const CComGITPtr& git);
CComGITPtr& operator= (DWORD dwCookie);
CComGITPtr& operator= (CComGITPtr&& rv);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `p`  
 インターフェイスへのポインター。  
  
 [入力] `git`  
 `CComGITPtr` オブジェクトへの参照。  
  
 [入力] `dwCookie`  
 インターフェイス ポインターの識別に使用する cookie です。  
  
 [入力] `rv`  
 `CComGITPtr`からデータを移動します。  
  
### <a name="return-value"></a>戻り値  
 更新されたを返します`CComGITPtr`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 新しい値を割り当てます、`CComGITPtr`既存のオブジェクトとは、グローバル インターフェイス テーブルへの参照からのオブジェクト。  
  
##  <a name="operator_dword"></a>  CComGITPtr::operator DWORD  
 関連付けられた cookie を返し、`CComGITPtr`オブジェクト。  
  
```  
operator DWORD() const;
```  
  
### <a name="remarks"></a>コメント  
 Cookie は、インターフェイスとその場所の識別に使用される変数です。  
  
##  <a name="revoke"></a>  CComGITPtr::Revoke  
 グローバル インターフェイス テーブル (GIT) から現在のインターフェイスを削除するには、このメソッドを呼び出します。  
  
```
HRESULT Revoke() throw();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 GIT からのインターフェイスを削除します。  
  
## <a name="see-also"></a>関連項目  
 [フリー スレッド マーシャラー](../../atl/atl-and-the-free-threaded-marshaler.md)   
 [アパートメント間でインターフェイスへのアクセス](http://msdn.microsoft.com/library/windows/desktop/ms682353)   
 [グローバル インターフェイス テーブルを使用する場合](http://msdn.microsoft.com/library/windows/desktop/ms693729)   
 [クラスの概要](../../atl/atl-class-overview.md)
