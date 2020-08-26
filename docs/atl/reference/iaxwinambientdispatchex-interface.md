---
title: IAxWinAmbientDispatchEx インターフェイス
ms.date: 11/04/2016
f1_keywords:
- IAxWinAmbientDispatchEx
- ATLIFACE/ATL::IAxWinAmbientDispatchEx
- ATLIFACE/ATL::SetAmbientDispatch
helpviewer_keywords:
- IAxWinAmbientDispatchEx interface
ms.assetid: 2c25e079-6128-4278-bc72-b2c6195ba7ef
ms.openlocfilehash: f052c39424fc2ee6f43f249e3034be7c464d016c
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833388"
---
# <a name="iaxwinambientdispatchex-interface"></a>IAxWinAmbientDispatchEx インターフェイス

このインターフェイスは、ホストされるコントロールの追加のアンビエントプロパティを実装します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
MIDL_INTERFACE("B2D0778B - AC99 - 4c58 - A5C8 - E7724E5316B5") IAxWinAmbientDispatchEx : public IAxWinAmbientDispatch
```

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|名前|説明|
|-|-|
|[SetAmbientDispatch](#setambientdispatch)|このメソッドは、ユーザー定義のインターフェイスを使用して、既定のアンビエントプロパティインターフェイスを補うために呼び出されます。|

## <a name="remarks"></a>解説

ATL に静的にリンクされている ATL アプリケーションにこのインターフェイスを含め、ActiveX コントロール、特にアンビエントプロパティを持つ ActiveX コントロールをホストします。 このインターフェイスを含めないと、次のアサーションが生成されます。 "LIBID を CComModule:: Init に渡すことは忘れました"

このインターフェイスは、ATL の ActiveX コントロールのホストオブジェクトによって公開されます。 [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)から派生したメソッドを追加します。このメソッドを使用すると、 `IAxWinAmbientDispatchEx` ATL によって提供されるアンビエントプロパティインターフェイスを独自のものに補完することができます。

<xref:System.Windows.Forms.AxHost> は、 `IAxWinAmbientDispatch` `IAxWinAmbientDispatchEx` コードが格納されているタイプライブラリに関する型情報の読み込みを試みます。

ATL90.dll にリンクしている場合、 **AXHost** は DLL のタイプライブラリから型情報を読み込みます。

詳細については、「 [ATL AXHost を使用した ActiveX コントロールのホスト](../../atl/hosting-activex-controls-using-atl-axhost.md) 」を参照してください。

## <a name="requirements"></a>必要条件

このインターフェイスの定義は、次の表に示すように、さまざまな形式で使用できます。

|定義の種類|ファイル|
|---------------------|----------|
|IDL|atliface|
|タイプライブラリ|ATL.dll|
|C++|atliface (ATLBase. h にも含まれる)|

## <a name="iaxwinambientdispatchexsetambientdispatch"></a><a name="setambientdispatch"></a> IAxWinAmbientDispatchEx::SetAmbientDispatch

このメソッドは、ユーザー定義のインターフェイスを使用して、既定のアンビエントプロパティインターフェイスを補うために呼び出されます。

```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```

### <a name="parameters"></a>パラメーター

*pDispatch*<br/>
新しいインターフェイスへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="remarks"></a>解説

`SetAmbientDispatch`新しいインターフェイスへのポインターを使用してを呼び出すと、そのプロパティが[IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)によってまだ提供されていない場合に、ホストされているコントロールによって要求されたプロパティやメソッドを呼び出すために、この新しいインターフェイスが使用されます。

## <a name="see-also"></a>関連項目

[IAxWinAmbientDispatch インターフェイス](../../atl/reference/iaxwinambientdispatch-interface.md)
