---
title: IAxWinAmbientDispatchEx インターフェイス |Microsoft Docs
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
ms.openlocfilehash: e579c537421eba0f3b9dbcf347e08b6691cddb21
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022215"
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
|[SetAmbientDispatch](#setambientdispatch)|このメソッドはユーザー定義のインターフェイスを持つ既定のアンビエント プロパティのインターフェイスを補完します。|

## <a name="remarks"></a>Remarks

ATL アプリケーションの ATL と ActiveX コントロール、特にアンビエント プロパティを持つ ActiveX コントロールのホストに静的にリンクされている、このインターフェイスがあります。 このアサーションの生成はこのインターフェイスは含まれません:「を忘れました:term に LIBID を渡す」

このインターフェイスは、オブジェクトのホスト、ATL の ActiveX コントロールによって公開されます。 派生した[IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)、`IAxWinAmbientDispatchEx`を独自のいずれかで、ATL によって提供されるアンビエント プロパティのインターフェイスを補うことができるメソッドを追加します。

[AXHost](https://msdn.microsoft.com/library/system.windows.forms.axhost.aspx)をに関する型情報を読み込んでみます`IAxWinAmbientDispatch`と`IAxWinAmbientDispatchEx`コードを含むタイプ ライブラリから。

ATL90.dll にリンクしている場合**AXHost**は DLL 内のタイプ ライブラリから型情報を読み込みます。

参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)の詳細。

## <a name="requirements"></a>要件

このインターフェイスの定義は、次の表に示すようにさまざまな形式で使用できます。

|定義の種類|ファイル|
|---------------------|----------|
|IDL|atliface.idl|
|タイプ ライブラリ|ATL.dll|
|C++|atliface.h (ATLBase.h にも含まれています)|

##  <a name="setambientdispatch"></a>  IAxWinAmbientDispatchEx::SetAmbientDispatch

このメソッドはユーザー定義のインターフェイスを持つ既定のアンビエント プロパティのインターフェイスを補完します。

```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```

### <a name="parameters"></a>パラメーター

*pDispatch*<br/>
新しいインターフェイスへのポインター。

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

### <a name="remarks"></a>Remarks

ときに`SetAmbientDispatch`呼びますプロパティやメソッドでこれらのプロパティが既に提供されていない場合、ホストされるコントロールでのよく寄せられるすべての呼び出しに、この新しいインターフェイスを使用と新しいインターフェイスへのポインター、 [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md).

## <a name="see-also"></a>関連項目

[IAxWinAmbientDispatch インターフェイス](../../atl/reference/iaxwinambientdispatch-interface.md)
