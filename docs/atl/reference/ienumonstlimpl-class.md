---
title: つまりクラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IEnumOnSTLImpl
- ATLCOM/ATL::IEnumOnSTLImpl
- ATLCOM/ATL::IEnumOnSTLImpl::Clone
- ATLCOM/ATL::IEnumOnSTLImpl::Init
- ATLCOM/ATL::IEnumOnSTLImpl::Next
- ATLCOM/ATL::IEnumOnSTLImpl::Reset
- ATLCOM/ATL::IEnumOnSTLImpl::Skip
- ATLCOM/ATL::IEnumOnSTLImpl::m_iter
- ATLCOM/ATL::IEnumOnSTLImpl::m_pcollection
- ATLCOM/ATL::IEnumOnSTLImpl::m_spUnk
dev_langs:
- C++
helpviewer_keywords:
- IEnumOnSTLImpl class
ms.assetid: 1789e77b-88b8-447d-a490-806b918912ce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1de4bdd0d07e694303f850d6298d77afe3322214
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365257"
---
# <a name="ienumonstlimpl-class"></a>つまりクラス
このクラスは、C++ 標準ライブラリ コレクションに基づく列挙子インターフェイスを定義します。  
  
## <a name="syntax"></a>構文  
  
```
template <class Base,
    const IID* piid, class T, class Copy, class CollType>  
class ATL_NO_VTABLE IEnumOnSTLImpl : public Base
```  
  
#### <a name="parameters"></a>パラメーター  
 `Base`  
 COM の列挙子 ([として](https://msdn.microsoft.com/library/ms680089.aspx)) インターフェイス。  
  
 `piid`  
 列挙子インターフェイスのインターフェイス ID へのポインター。  
  
 `T`  
 列挙子インターフェイスによって公開されている項目の種類。  
  
 `Copy`  
 A[コピー ポリシー クラス](../../atl/atl-copy-policy-classes.md)です。  
  
 `CollType`  
 C++ 標準ライブラリのコンテナー クラスです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IEnumOnSTLImpl::Clone](#clone)|実装[IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx)です。|  
|[保ちます](#init)|列挙子を初期化します。|  
|[IEnumOnSTLImpl::Next](#next)|実装[IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx)です。|  
|[IEnumOnSTLImpl::Reset](#reset)|実装[IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx)です。|  
|[IEnumOnSTLImpl::Skip](#skip)|実装[IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx)です。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[IEnumOnSTLImpl::m_iter](#m_iter)|コレクション内の列挙子の現在位置を表す反復子。|  
|[IEnumOnSTLImpl::m_pcollection](#m_pcollection)|列挙するアイテムを保持している C++ 標準ライブラリのコンテナーへのポインター。|  
|[IEnumOnSTLImpl::m_spUnk](#m_spunk)|**IUnknown**コレクションを提供するオブジェクトのポインター。|  
  
## <a name="remarks"></a>コメント  
 `IEnumOnSTLImpl` C++ 標準ライブラリと互換性のあるコンテナーで列挙されている項目を格納する場所、COM の列挙子インターフェイスの実装を提供します。 このクラスと似ています、 [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)配列に基づいて、クラス、列挙子インターフェイスの実装を提供します。  
  
> [!NOTE]
>  参照してください[保ちます](../../atl/reference/ccomenumimpl-class.md#init)の詳細については、さらに違い`CComEnumImpl`と`IEnumOnSTLImpl`です。  
  
 通常、*いない*このインターフェイスの実装から派生することで、独自の列挙子クラスを作成する必要があります。 インスタンスを作成する方が一般的では、C++ 標準ライブラリのコンテナーに基づく ATL が指定した列挙子を使用する場合は、 [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)、から派生することで列挙子を返しますコレクションクラスを作成または[単独](../../atl/reference/icollectiononstlimpl-class.md)です。  
  
 ただし、(たとえば、1 つだけでなく、列挙子インターフェイスのインターフェイスを公開する) カスタム列挙子を提供する必要がある場合は、このクラスから派生できます。 このような状況においてはほとんどをオーバーライドする必要があります、[クローン](#clone)独自の実装を提供するメソッド。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `Base`  
  
 `IEnumOnSTLImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="init"></a>  保ちます  
 列挙子を初期化します。  
  
```
HRESULT Init(
    IUnknown* pUnkForRelease,
    CollType& collection);
```  
  
### <a name="parameters"></a>パラメーター  
 `pUnkForRelease`  
 [in]**IUnknown**保持している必要がある列挙子の有効期間中にオブジェクトのポインター。 渡す**NULL**このようなオブジェクトが存在しない場合。  
  
 `collection`  
 列挙するアイテムを格納する C++ 標準ライブラリのコンテナーへの参照。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 渡す場合`Init`別のオブジェクトでは、コレクションへの参照を保持することができますを使用して、`pUnkForRelease`を確実に保持しているコレクション、オブジェクトとの使用可能な限り、列挙子が必要とするパラメーターです。  
  
 クライアントに返す列挙子インターフェイスへのポインターを渡す前に、このメソッドを呼び出す必要があります。  
  
##  <a name="clone"></a>  IEnumOnSTLImpl::Clone  
 このメソッドの実装を提供する、 [IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx)メソッド型のオブジェクトを作成することで`CComEnumOnSTL`、同じコレクションと、現在のオブジェクトによって使用される反復子で初期化してにインターフェイスを返す新しく作成されたオブジェクト。  
  
```
STDMETHOD(Clone)(Base** ppEnum);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppEnum`  
 [out]新しく作成されたオブジェクトの列挙子インターフェイスは、現在の列挙子から複製されます。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="m_spunk"></a>  IEnumOnSTLImpl::m_spUnk  
 **IUnknown**コレクションを提供するオブジェクトのポインター。  
  
```
CComPtr<IUnknown> m_spUnk;
```  
  
### <a name="remarks"></a>コメント  
 このスマート ポインターに渡されるオブジェクトの参照を保持する[保ちます](#init)、残っているアライブ列挙子の有効期間中にことを確認します。  
  
##  <a name="m_pcollection"></a>  IEnumOnSTLImpl::m_pcollection  
 このメンバーは、列挙子インターフェイスの実装で処理するデータを提供するコレクションを指します。  
  
```
CollType* m_pcollection;
```  
  
### <a name="remarks"></a>コメント  
 このメンバーはへの呼び出しによって初期化[保ちます](#init)です。  
  
##  <a name="m_iter"></a>  IEnumOnSTLImpl::m_iter  
 このメンバーは、コレクション内の現在位置をマークし、後続の要素に移動するために使用する反復子を保持します。  
  
```
CollType::iterator m_iter;
```  
  
##  <a name="next"></a>  IEnumOnSTLImpl::Next  
 このメソッドの実装を提供する、 [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx)メソッドです。  
  
```
STDMETHOD(Next)(
    ULONG celt,
    T* rgelt,
    ULONG* pceltFetched);
```  
  
### <a name="parameters"></a>パラメーター  
 `celt`  
 [in]要求された要素の数。  
  
 `rgelt`  
 [out]要素を使用して入力する配列。  
  
 `pceltFetched`  
 [out]実際に返される要素の数`rgelt`です。 これより小さい`celt`場合よりも少ない`celt`要素がリストに残ります。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="reset"></a>  IEnumOnSTLImpl::Reset  
 このメソッドの実装を提供する、 [IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx)メソッドです。  
  
```
STDMETHOD(Reset)(void);
```  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="skip"></a>  IEnumOnSTLImpl::Skip  
 このメソッドの実装を提供する、 [IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx)メソッドです。  
  
```
STDMETHOD(Skip)(ULONG celt);
```  
  
### <a name="parameters"></a>パラメーター  
 `celt`  
 [in]スキップする要素の数。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
