---
title: IAxWinAmbientDispatchEx インターフェイス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IAxWinAmbientDispatchEx
- ATLIFACE/ATL::IAxWinAmbientDispatchEx
- ATLIFACE/ATL::SetAmbientDispatch
dev_langs:
- C++
helpviewer_keywords:
- IAxWinAmbientDispatchEx interface
ms.assetid: 2c25e079-6128-4278-bc72-b2c6195ba7ef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 22815ddf3131b9d262d68a3202f4f500b7edf807
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="iaxwinambientdispatchex-interface"></a>IAxWinAmbientDispatchEx インターフェイス
このインターフェイスは、ホストされるコントロールの補足のアンビエント プロパティを実装します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
MIDL_INTERFACE("B2D0778B - AC99 - 4c58 - A5C8 - E7724E5316B5") IAxWinAmbientDispatchEx : public IAxWinAmbientDispatch
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[SetAmbientDispatch](#setambientdispatch)|ユーザー定義のインターフェイスを持つ既定のアンビエント プロパティ インターフェイスを補完する、このメソッドが呼び出されます。|  
  
## <a name="remarks"></a>コメント  
 ATL アプリケーションの ATL および ActiveX コントロールは、特にアンビエント プロパティを持つ ActiveX コントロールのホストに静的にリンクされている、このインターフェイスがあります。 このインターフェイスを含めないと、このアサーションが生成されます:「を忘れましたか ccommodule::init に LIBID を渡す」  
  
 このインターフェイスは、ATL の ActiveX コントロールをホストしているオブジェクトによって公開されます。 派生[IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)、`IAxWinAmbientDispatchEx`独自のいずれかの ATL によって提供されるアンビエント プロパティ インターフェイスを補完できるようにするメソッドを追加します。  
  
 [AXHost](https://msdn.microsoft.com/library/system.windows.forms.axhost.aspx)をに関する型情報を読み込んでみます`IAxWinAmbientDispatch`と`IAxWinAmbientDispatchEx`コードが含まれるタイプ ライブラリからです。  
  
 ATL90.dll にリンクする場合は**AXHost**が DLL 内のタイプ ライブラリから型情報を読み込みます。  
  
 参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)詳細についてはします。  
  
## <a name="requirements"></a>要件  
 このインターフェイスの定義は、次の表に示すようにさまざまな形式で使用できます。  
  
|定義の型|ファイル|  
|---------------------|----------|  
|IDL|atliface.idl|  
|タイプ ライブラリ|ATL.dll|  
|C++|atliface.h (ATLBase.h にも含まれます)|  
  
##  <a name="setambientdispatch"></a>  IAxWinAmbientDispatchEx::SetAmbientDispatch  
 ユーザー定義のインターフェイスを持つ既定のアンビエント プロパティ インターフェイスを補完する、このメソッドが呼び出されます。  
  
```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 *pDispatch*  
 新しいインターフェイスへのポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 ときに`SetAmbientDispatch`が呼び出された任意のプロパティまたはメソッドから求められる、ホストされるコントロールでこれらのプロパティは既に提供されない場合の呼び出しに、この新しいインターフェイスを使用で新しいインターフェイスへのポインター、 [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md).  
  
## <a name="see-also"></a>関連項目  
 [IAxWinAmbientDispatch インターフェイス](../../atl/reference/iaxwinambientdispatch-interface.md)
