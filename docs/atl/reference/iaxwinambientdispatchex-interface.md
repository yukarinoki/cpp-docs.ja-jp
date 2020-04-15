---
title: インターフェイス
ms.date: 11/04/2016
f1_keywords:
- IAxWinAmbientDispatchEx
- ATLIFACE/ATL::IAxWinAmbientDispatchEx
- ATLIFACE/ATL::SetAmbientDispatch
helpviewer_keywords:
- IAxWinAmbientDispatchEx interface
ms.assetid: 2c25e079-6128-4278-bc72-b2c6195ba7ef
ms.openlocfilehash: f4816846801e388619db62998ec979a1100916ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329976"
---
# <a name="iaxwinambientdispatchex-interface"></a>インターフェイス

このインターフェイスは、ホストされたコントロールの補足的なアンビエント プロパティを実装します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
MIDL_INTERFACE("B2D0778B - AC99 - 4c58 - A5C8 - E7724E5316B5") IAxWinAmbientDispatchEx : public IAxWinAmbientDispatch
```

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[アンビエントディスパッチの設定](#setambientdispatch)|このメソッドは、既定のアンビエント プロパティ インターフェイスをユーザー定義インターフェイスで補完するために呼び出されます。|

## <a name="remarks"></a>解説

このインターフェイスは、ATL に静的にリンクされ、ActiveX コントロール 、特にアンビエント プロパティを持つ ActiveX コントロールに静的にリンクされている ATL アプリケーションに含めます。 このインターフェイスを含まないと、このアサーションが生成されます: "LIBID を CCom モジュールに渡すことを忘れたのは、次のとおりです: Init "

このインターフェイスは、ATL の ActiveX コントロールホスト オブジェクトによって公開されます。 [から](../../atl/reference/iaxwinambientdispatch-interface.md)派生したメソッドを`IAxWinAmbientDispatchEx`追加すると、ATL によって提供されるアンビエント プロパティ インターフェイスを独自のインターフェイスで補完できます。

<xref:System.Windows.Forms.AxHost>コードを含むタイプ ライブラリ`IAxWinAmbientDispatch`に`IAxWinAmbientDispatchEx`関する型情報と、コードを含むタイプ ライブラリから型情報を読み込もうとします。

ATL90.dll にリンクしている場合 **、AXHost**はタイプ ライブラリから DLL に型情報を読み込みます。

詳細については[、ATL AXHost を使用した ActiveX コントロールのホスティング](../../atl/hosting-activex-controls-using-atl-axhost.md)を参照してください。

## <a name="requirements"></a>必要条件

このインターフェイスの定義は、次の表に示すように、さまざまな形式で使用できます。

|定義タイプ|ファイル|
|---------------------|----------|
|Idl|アトリファス.idl|
|タイプ ライブラリ|ATL.dll|
|C++|atliface.h (ATLBase.h にも含まれています)|

## <a name="iaxwinambientdispatchexsetambientdispatch"></a><a name="setambientdispatch"></a>IAxWin アンビエントディスパッチエックス::設定アンビエントディスパッチ

このメソッドは、既定のアンビエント プロパティ インターフェイスをユーザー定義インターフェイスで補完するために呼び出されます。

```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```

### <a name="parameters"></a>パラメーター

*ディスパッチ*<br/>
新しいインターフェイスへのポインター。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

新`SetAmbientDispatch`しいインターフェイスへのポインターを使用して呼び出されると、この新しいインターフェイスは、[ホスト](../../atl/reference/iaxwinambientdispatch-interface.md)されたコントロールによって求められるプロパティまたはメソッドを呼び出すために使用されます。

## <a name="see-also"></a>関連項目

[インターフェイス](../../atl/reference/iaxwinambientdispatch-interface.md)
