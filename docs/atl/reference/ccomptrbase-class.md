---
title: CComPtrBase クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComPtrBase
- ATLCOMCLI/ATL::CComPtrBase
- ATLCOMCLI/ATL::CComPtrBase::Advise
- ATLCOMCLI/ATL::CComPtrBase::Attach
- ATLCOMCLI/ATL::CComPtrBase::CoCreateInstance
- ATLCOMCLI/ATL::CComPtrBase::CopyTo
- ATLCOMCLI/ATL::CComPtrBase::Detach
- ATLCOMCLI/ATL::CComPtrBase::IsEqualObject
- ATLCOMCLI/ATL::CComPtrBase::QueryInterface
- ATLCOMCLI/ATL::CComPtrBase::Release
- ATLCOMCLI/ATL::CComPtrBase::SetSite
- ATLCOMCLI/ATL::CComPtrBase::p
dev_langs:
- C++
helpviewer_keywords:
- CComPtrBase class
ms.assetid: 6dbe9543-dee8-4a97-b02f-dd3a25f4a1a0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ea90c1394da9b6a202b121a0e521f99acaba8264
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366368"
---
# <a name="ccomptrbase-class"></a>CComPtrBase クラス
このクラスは、メモリの COM ベースのルーチンを使用するスマート ポインター クラスの基礎を提供します。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
class CComPtrBase
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 スマート ポインターが参照するオブジェクトの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComPtrBase:: ~ CComPtrBase](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComPtrBase::Advise](#advise)|間の接続を作成するには、このメソッドを呼び出して、`CComPtrBase`のコネクション ポイントとクライアントのシンク。|  
|[CComPtrBase::Attach](#attach)|このメソッドを呼び出して既存のポインターの所有権を取得します。|  
|[CComPtrBase::CoCreateInstance](#cocreateinstance)|指定したクラス ID、またはプログラムの ID に関連付けられているクラスのオブジェクトを作成するには、このメソッドを呼び出す|  
|[CComPtrBase::CopyTo](#copyto)|コピーするには、このメソッドを呼び出す、`CComPtrBase`別のポインター変数を指すポインターです。|  
|[CComPtrBase::Detach](#detach)|ポインターの所有権を解放するには、このメソッドを呼び出します。|  
|[CComPtrBase::IsEqualObject](#isequalobject)|かどうか確認するには、このメソッドを呼び出して、指定した**IUnknown**に関連付けられている同じオブジェクトを指す、`CComPtrBase`オブジェクト。|  
|[CComPtrBase::QueryInterface](#queryinterface)|指定したインターフェイスへのポインターを返すには、このメソッドを呼び出します。|  
|[CComPtrBase::Release](#release)|インターフェイスを解放するには、このメソッドを呼び出します。|  
|[CComPtrBase::SetSite](#setsite)|サイトを設定するには、このメソッドを呼び出して、`CComPtrBase`オブジェクトを**IUnknown**の親オブジェクトです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CComPtrBase::operator T *](#operator_t_star)|キャスト演算子です。|  
|[CComPtrBase::operator!](#operator_not)|NOT 演算子です。|  
|[CComPtrBase::operator (& a)](#operator_amp)|(& A) 演算子。|  
|[CComPtrBase::operator *](#operator_star)|* 演算子。|  
|[CComPtrBase::operator <](#ccomptrbase__operator lt)|小さいの演算子よりもします。|  
|[CComPtrBase::operator = =](#operator_eq_eq)|等値演算子。|  
|[CComPtrBase::operator -> します。](#operator_ptr)|メンバーへのポインター演算子です。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[解放](#p)|ポインターのデータ メンバー変数です。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、COM メモリ管理ルーチンを使用するその他のスマート ポインターの基盤[CComQIPtr](../../atl/reference/ccomqiptr-class.md)と[CComPtr](../../atl/reference/ccomptr-class.md)です。 派生クラスは、独自のコンス トラクターと演算子がによって提供されるメソッドに依存して`CComPtrBase`です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcomcli.h  
  
##  <a name="advise"></a>  CComPtrBase::Advise  
 間の接続を作成するには、このメソッドを呼び出して、`CComPtrBase`のコネクション ポイントとクライアントのシンク。  
  
```
HRESULT Advise(
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnk*  
 クライアントへのポインター **IUnknown**です。  
  
 `iid`  
 接続ポイントの GUID です。 通常、これは、接続ポイントによって管理されている着信インターフェイスと同じです。  
  
 `pdw`  
 接続を一意に識別するクッキーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 参照してください[AtlAdvise](connection-point-global-functions.md#atladvise)詳細についてはします。  
  
##  <a name="attach"></a>  CComPtrBase::Attach  
 このメソッドを呼び出して既存のポインターの所有権を取得します。  
  
```
void Attach(T* p2) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p2`  
 `CComPtrBase` This ポインターの所有権を持つオブジェクト。  
  
### <a name="remarks"></a>コメント  
 **アタッチ**呼び出し[CComPtrBase::Release](#release)既存の[解放](#p)メンバー変数を示し、代入`p2`に`CComPtrBase::p`です。 ときに、`CComPtrBase`オブジェクト ポインターの所有権を自動的に呼び出されます`Release`ポインターといずれかが削除されるポインターに割り当てられたデータで、オブジェクトの参照カウントが 0 になった場合。  
  
##  <a name="dtor"></a>  CComPtrBase:: ~ CComPtrBase  
 デストラクターです。  
  
```
~CComPtrBase() throw();
```  
  
### <a name="remarks"></a>コメント  
 によって示されるインターフェイスを解放`CComPtrBase`です。  
  
##  <a name="cocreateinstance"></a>  CComPtrBase::CoCreateInstance  
 指定したクラス ID、またはプログラムの ID に関連付けられているクラスのオブジェクトを作成するには、このメソッドを呼び出す  
  
```
HRESULT CoCreateInstance(  
    LPCOLESTR szProgID,
    LPUNKNOWN pUnkOuter = NULL,
    DWORD dwClsContext = CLSCTX_ALL) throw();

HRESULT CoCreateInstance(  
    REFCLSID rclsid,
    LPUNKNOWN pUnkOuter = NULL,
    DWORD dwClsContext = CLSCTX_ALL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `szProgID`  
 CLSID の回復に使用される、ProgID へのポインター。  
  
 `pUnkOuter`  
 場合**NULL**集計の一部として、オブジェクトが作成されていないことを示します。 場合以外**NULL**、集約オブジェクトへのポインターは、 **IUnknown**インターフェイス (制御**IUnknown**)。  
  
 `dwClsContext`  
 新しく作成されたオブジェクトを管理するコードを実行するコンテキスト。  
  
 `rclsid`  
 データとオブジェクトの作成に使用されるコードに関連付けられた CLSID。  
  
### <a name="return-value"></a>戻り値  
 エラー発生時に成功した場合、または REGDB_E_CLASSNOTREG、CLASS_E_NOAGGREGATION、CO_E_CLASSSTRING または E_NOINTERFACE に S_OK を返します。 参照してください[とも](http://msdn.microsoft.com/library/windows/desktop/ms686615)と[この](http://msdn.microsoft.com/library/windows/desktop/ms688386)これらのエラーの詳細についてはします。  
  
### <a name="remarks"></a>コメント  
 メソッドの最初のフォームが呼び出されると、[この](http://msdn.microsoft.com/library/windows/desktop/ms688386)CLSID を回復するために使用します。 両方の形式[とも](http://msdn.microsoft.com/library/windows/desktop/ms686615)します。  
  
 デバッグ ビルドで、アサーション エラーが発生場合[解放](#p)が NULL と等しくありません。  
  
##  <a name="copyto"></a>  CComPtrBase::CopyTo  
 コピーするには、このメソッドを呼び出す、`CComPtrBase`別のポインター変数を指すポインターです。  
  
```
HRESULT CopyTo(T** ppT) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *ppT*  
 受け取る変数のアドレス、`CComPtrBase`ポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、エラー発生時に E_POINTER S_OK を返します。  
  
### <a name="remarks"></a>コメント  
 コピー、`CComPtrBase`へのポインター *ppT*です。 参照カウント、[解放](#p)メンバー変数が増加します。  
  
 場合に返される HRESULT エラー *ppT*が NULL です。 デバッグ ビルドで、アサーション エラーが発生場合*ppT*が NULL です。  
  
##  <a name="detach"></a>  CComPtrBase::Detach  
 ポインターの所有権を解放するには、このメソッドを呼び出します。  
  
```
T* Detach() throw();
```  
  
### <a name="return-value"></a>戻り値  
 ポインターのコピーを返します。  
  
### <a name="remarks"></a>コメント  
 ポインターの所有権を解放、[解放](#p)データ メンバー変数に NULL ポインターのコピーを返します。  
  
##  <a name="isequalobject"></a>  CComPtrBase::IsEqualObject  
 かどうか確認するには、このメソッドを呼び出して、指定した**IUnknown**に関連付けられている同じオブジェクトを指す、`CComPtrBase`オブジェクト。  
  
```
bool IsEqualObject(IUnknown* pOther) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pOther`  
 **IUnknown \*** を比較します。  
  
### <a name="return-value"></a>戻り値  
 オブジェクトは同一の場合は false をそれ以外の場合がある場合は true を返します。  
  
##  <a name="operator_not"></a>  CComPtrBase::operator!  
 NOT 演算子です。  
  
```
bool operator!() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 場合は true を返します、`CComHeapPtr`ポインターが NULL、false それ以外の場合。  
  
##  <a name="operator_amp"></a>  CComPtrBase::operator &amp;  
 (& A) 演算子。  
  
```
T** operator&() throw();
```  
  
### <a name="return-value"></a>戻り値  
 によって指されるオブジェクトのアドレスを返します、`CComPtrBase`オブジェクト。  
  
##  <a name="operator_star"></a>  CComPtrBase::operator *  
 * 演算子。  
  
```
T& operator*() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 値を返します[解放](#p); によって参照されるオブジェクトへのポインターは、`CComPtrBase`オブジェクト。  
  
 場合に、アサーション エラーが発生する場合は、デバッグ ビルド[解放](#p)が NULL と等しくありません。  
  
##  <a name="operator_eq_eq"></a>  CComPtrBase::operator = =  
 等値演算子。  
  
```
bool operator== (T* pT) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *pT*  
 オブジェクトへのポインター。  
  
### <a name="return-value"></a>戻り値  
 場合は true を返します`CComPtrBase`と*pT*オブジェクトを指す同じ、false それ以外の場合。  
  
##  <a name="operator_ptr"></a>  CComPtrBase::operator-&gt;  

 メンバーへのポインター演算子です。  
  
```
_NoAddRefReleaseOnCComPtr<T>* operator->() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 値を返します、[解放](#p)データ メンバー変数。  
  
### <a name="remarks"></a>コメント  
 この演算子によって示されるクラスのメソッドを呼び出すを使用して、`CComPtrBase`オブジェクト。 デバッグ ビルドで、アサーション場合にエラーが発生、`CComPtrBase`データ メンバーが NULL をポイントします。  
  
##  <a name="operator_lt"></a>  CComPtrBase::operator &lt;  
 小さいの演算子よりもします。  
  
```
bool operator<(T* pT) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *pT*  
 オブジェクトへのポインター。  
  
### <a name="return-value"></a>戻り値  
 ポインターが現在のオブジェクトによって管理されている場合、true を返しますでは、比較するポインターより小さいです。  
  
##  <a name="operator_t_star"></a>  CComPtrBase::operator T *  
 キャスト演算子です。  
  
```  
operator T*() const throw();
```  
  
### <a name="remarks"></a>コメント  
 クラス テンプレートで定義されたオブジェクト データ型へのポインターを返します。  
  
##  <a name="p"></a>  解放  
 ポインターのデータ メンバー変数です。  
  
```
T* p;
```  
  
### <a name="remarks"></a>コメント  
 このメンバー変数は、ポインターの情報を保持します。  
  
##  <a name="queryinterface"></a>  CComPtrBase::QueryInterface  
 指定したインターフェイスへのポインターを返すには、このメソッドを呼び出します。  
  
```
template <class Q> HRESULT QueryInterface(Q
** pp) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `Q`  
 あるインターフェイス ポインターが必要なオブジェクトの型。  
  
 `pp`  
 要求されたインターフェイス ポインターを受け取る出力変数のアドレス。  
  
### <a name="return-value"></a>戻り値  
 エラー発生時に成功した場合、または E_NOINTERFACE S_OK を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出す[iunknown::queryinterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)です。  
  
 デバッグ ビルドで、アサーション エラーが発生場合*pp*が NULL と等しくありません。  
  
##  <a name="release"></a>  CComPtrBase::Release  
 インターフェイスを解放するには、このメソッドを呼び出します。  
  
```
void Release() throw();
```  
  
### <a name="remarks"></a>コメント  
 インターフェイスが解放されると、および[解放](#p)は NULL に設定します。  
  
##  <a name="setsite"></a>  CComPtrBase::SetSite  
 サイトを設定するには、このメソッドを呼び出して、`CComPtrBase`オブジェクトを**IUnknown**の親オブジェクトです。  
  
```
HRESULT SetSite(IUnknown* punkParent) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `punkParent`  
 ポインター、 **IUnknown**親のインターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出す[AtlSetChildSite](composite-control-global-functions.md#atlsetchildsite)です。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
