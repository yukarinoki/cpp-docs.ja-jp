---
title: CComEnumImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComEnumImpl
- ATLCOM/ATL::CComEnumImpl
- ATLCOM/ATL::CComEnumImpl::CComEnumImpl
- ATLCOM/ATL::CComEnumImpl::Clone
- ATLCOM/ATL::CComEnumImpl::Init
- ATLCOM/ATL::CComEnumImpl::Next
- ATLCOM/ATL::CComEnumImpl::Reset
- ATLCOM/ATL::CComEnumImpl::Skip
- ATLCOM/ATL::CComEnumImpl::m_begin
- ATLCOM/ATL::CComEnumImpl::m_dwFlags
- ATLCOM/ATL::CComEnumImpl::m_end
- ATLCOM/ATL::CComEnumImpl::m_iter
- ATLCOM/ATL::CComEnumImpl::m_spUnk
dev_langs:
- C++
helpviewer_keywords:
- CComEnumImpl class
ms.assetid: cc0d8e76-e608-46db-87cd-4c7161fe32d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 14c7b1e72db3337b786a0e524ae3d8da964f6bbc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365029"
---
# <a name="ccomenumimpl-class"></a>CComEnumImpl クラス
このクラスは、配列内に列挙されている項目が格納 COM 列挙子インターフェイスの実装を提供します。  
  
## <a name="syntax"></a>構文  
  
```
template <class Base,
    const IID* piid, class T, class Copy>  
class ATL_NO_VTABLE CComEnumImpl : public Base
```  
  
#### <a name="parameters"></a>パラメーター  
 `Base`  
 COM の列挙子 ([として](https://msdn.microsoft.com/library/ms680089.aspx)) インターフェイス。  
  
 `piid`  
 列挙子インターフェイスのインターフェイス ID へのポインター。  
  
 `T`  
 列挙子インターフェイスによって公開されている項目の種類。  
  
 `Copy`  
 同種[コピー ポリシー クラス](../../atl/atl-copy-policy-classes.md)です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComEnumImpl::CComEnumImpl](#ccomenumimpl)|コンストラクターです。|  
|[CComEnumImpl:: ~ CComEnumImpl](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComEnumImpl::Clone](#clone)|実装[IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx)です。|  
|[保ちます](#init)|列挙子を初期化します。|  
|[CComEnumImpl::Next](#next)|実装[IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx)です。|  
|[CComEnumImpl::Reset](#reset)|実装[IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx)です。|  
|[より](#skip)|実装[IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx)です。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComEnumImpl::m_begin](#m_begin)|配列の最初の項目へのポインター。|  
|[CComEnumImpl::m_dwFlags](#m_dwflags)|を通じて渡されるコピー フラグ`Init`です。|  
|[CComEnumImpl::m_end](#m_end)|配列の最後の項目を越えた場所へのポインター。|  
|[CComEnumImpl::m_iter](#m_iter)|配列内の現在のアイテムへのポインター。|  
|[CComEnumImpl::m_spUnk](#m_spunk)|**IUnknown**列挙されているコレクションを提供するオブジェクトのポインター。|  
  
## <a name="remarks"></a>コメント  
 `CComEnumImpl` 配列内に列挙されている項目が格納 COM 列挙子インターフェイスの実装を提供します。 このクラスと似ています、`IEnumOnSTLImpl`列挙子インターフェイスの実装を提供するクラスは、C++ 標準ライブラリのコンテナーに基づいています。  
  
> [!NOTE]
>  詳細についてはさらに違いに`CComEnumImpl`と`IEnumOnSTLImpl`を参照してください[保ちます](#init)です。  
  
 通常、*いない*このインターフェイスの実装から派生することで、独自の列挙子クラスを作成する必要があります。 インスタンスを作成する方が一般的では、配列に基づく ATL が指定した列挙子を使用する場合は、[上記](../../atl/reference/ccomenum-class.md)です。  
  
 ただし、(たとえば、1 つだけでなく、列挙子インターフェイスのインターフェイスを公開する) カスタム列挙子を提供する必要がある場合は、このクラスから派生できます。 このような状況においてはほとんどをオーバーライドする必要があります、 [CComEnumImpl::Clone](#clone)独自の実装を提供するメソッド。  
  
 詳細については、次を参照してください。 [ATL のコレクションと列挙子](../../atl/atl-collections-and-enumerators.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `Base`  
  
 `CComEnumImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="ccomenumimpl"></a>  CComEnumImpl::CComEnumImpl  
 コンストラクターです。  
  
```
CComEnumImpl();
```  
  
##  <a name="dtor"></a>  CComEnumImpl:: ~ CComEnumImpl  
 デストラクターです。  
  
```
~CComEnumImpl();
```  
  
##  <a name="init"></a>  保ちます  
 クライアントに返す列挙子インターフェイスへのポインターを渡す前に、このメソッドを呼び出す必要があります。  
  
```
HRESULT Init(
    T* begin,
    T* end,
    IUnknown* pUnk,
    CComEnumFlags flags = AtlFlagNoCopy);
```  
  
### <a name="parameters"></a>パラメーター  
 *begin*  
 列挙するアイテムを含む配列の最初の要素へのポインター。  
  
 `end`  
 列挙するアイテムを含む配列の最後の要素の次の場所へのポインター。  
  
 *pUnk*  
 [in]**IUnknown**保持している必要がある列挙子の有効期間中にオブジェクトのポインター。 渡す**NULL**このようなオブジェクトが存在しない場合。  
  
 `flags`  
 列挙子が配列の所有権を取得する必要があるかどうか、またはそのコピーを作成かどうかを指定するフラグ。 使用可能な値は次のとおりです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 このメソッドを 1 回だけ呼び出す: 列挙子を初期化し、関数を使用して、破棄することです。  
  
 別のオブジェクトに保持されている配列内の項目にポインターを渡す場合 (データをコピーする列挙子を要求しない) 場合を使えば、 *pUnk*するが、オブジェクトと配列を保持している限り、列挙子の使用可能なパラメーターその必要があります。 列挙子には、それを維持するオブジェクトの COM 参照だけが保持されます。 列挙子が破棄されるときに、COM 参照が自動的に解放します。  
  
 `flags`パラメーターでは、列挙子が渡された配列の要素を処理する方法を指定することができます。 `flags` 値のいずれかを実行、**使用**次に示す列挙体。  
  
```  
enum CComEnumFlags  
   {  
   AtlFlagNoCopy = 0,  
   AtlFlagTakeOwnership = 2, // BitOwn  
   AtlFlagCopy = 3           // BitOwn | BitCopy  
   };  
```  
  
 **AtlFlagNoCopy**配列の有効期間が、列挙子によって制御されていないことを意味します。 この場合、いずれか、配列となります静的メソッドまたはで識別されるオブジェクト*pUnk*不要になったときに、配列を解放する責任があります。  
  
 **AtlFlagTakeOwnership**となる配列の破棄、列挙子によって制御されていることを意味します。 この場合、配列必要がありますが動的に割り当てられたを使用して**新しい**です。 列挙子は、デストラクターの中で配列を削除します。 通常、するには渡します**NULL**の*pUnk*何らかの理由により、列挙子の破棄の通知を受信する必要がある場合も、有効なポインターを渡すことができますが、します。  
  
 **AtlFlagCopy**は新しい配列が渡された配列にコピーすることによって作成されることを意味`Init`です。 新しい配列の有効期間は、列挙子によって制御されます。 列挙子は、デストラクターの中で配列を削除します。 通常、するには渡します**NULL**の*pUnk*何らかの理由により、列挙子の破棄の通知を受信する必要がある場合も、有効なポインターを渡すことができますが、します。  
  
> [!NOTE]
>  このメソッドのプロトタイプでは、配列の要素を指定の型として**T**ここで、 **T**クラスをテンプレート パラメーターとして定義されました。 これは COM インターフェイスのメソッドを使用して公開されている同じ種類[CComEnumImpl::Next](#next)です。 このこととは異なり[つまり](../../atl/reference/ienumonstlimpl-class.md)、このクラスは別の記憶域をサポートしていませんし、データ型を公開します。 配列内の要素のデータ型は COM インターフェイスで公開されているデータ型と同じである必要があります。  
  
##  <a name="clone"></a>  CComEnumImpl::Clone  
 このメソッドの実装を提供する、 [IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx)メソッド型のオブジェクトを作成することで`CComEnum`、同じ配列と、現在のオブジェクトによって使用される反復子で初期化してにインターフェイスを返す、新しく作成されたオブジェクト。  
  
```
STDMETHOD(Clone)(Base** ppEnum);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppEnum`  
 [out]新しく作成されたオブジェクトの列挙子インターフェイスは、現在の列挙子から複製されます。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 複製された列挙子しないように、独自に注意してください、元の列挙子が使用するデータのコピー (または所有権の取得)。 必要に応じて、複製された列挙子は維持元の列挙子 (COM の参照を使用) に必要な限りデータが使用できることを確認します。  
  
##  <a name="m_spunk"></a>  CComEnumImpl::m_spUnk  
 このスマート ポインターに渡されるオブジェクトの参照を保持する[保ちます](#init)、残っているアライブ列挙子の有効期間中にことを確認します。  
  
```
CComPtr<IUnknown> m_spUnk;
```  
  
##  <a name="m_begin"></a>  CComEnumImpl::m_begin  
 列挙するアイテムを含む配列の最後の要素の次の場所へのポインター。  
  
```
T* m_begin;
```  
  
##  <a name="m_end"></a>  CComEnumImpl::m_end  
 列挙するアイテムを含む配列の最初の要素へのポインター。  
  
```
T* m_end;
```  
  
##  <a name="m_iter"></a>  CComEnumImpl::m_iter  
 列挙するアイテムを含む配列の現在の要素へのポインター。  
  
```
T* m_iter;
```  
  
##  <a name="m_dwflags"></a>  CComEnumImpl::m_dwFlags  
 渡される、フラグ[保ちます](#init)です。  
  
```
DWORD m_dwFlags;
```  
  
##  <a name="next"></a>  CComEnumImpl::Next  
 このメソッドの実装を提供する、 [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx)メソッドです。  
  
```
STDMETHOD(Next)(ULONG celt, T* rgelt, ULONG* pceltFetched);
```  
  
### <a name="parameters"></a>パラメーター  
 `celt`  
 [in]要求された要素の数。  
  
 `rgelt`  
 [out]要素を格納する配列。  
  
 `pceltFetched`  
 [out]実際に返される要素の数`rgelt`です。 これより小さい`celt`場合よりも少ない`celt`要素が一覧に残っています。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="reset"></a>  CComEnumImpl::Reset  
 このメソッドの実装を提供する、 [IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx)メソッドです。  
  
```
STDMETHOD(Reset)(void);
```  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="skip"></a>  より  
 このメソッドの実装を提供する、 [IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx)メソッドです。  
  
```
STDMETHOD(Skip)(ULONG celt);
```  
  
### <a name="parameters"></a>パラメーター  
 `celt`  
 [in]スキップする要素の数。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 場合は、E_INVALIDARG を返します`celt`0 より小さい場合は S_FALSE を返します`celt`要素が返されると、それ以外の場合は S_OK を返します。  
  
## <a name="see-also"></a>関連項目  
 [つまりクラス](../../atl/reference/ienumonstlimpl-class.md)   
 [上記のクラス](../../atl/reference/ccomenum-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
