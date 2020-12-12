---
description: '詳細情報: CWinTraits クラス'
title: CWinTraits クラス
ms.date: 11/04/2016
f1_keywords:
- CWinTraits
- ATLWIN/ATL::CWinTraits
- ATLWIN/ATL::CWinTraits::GetWndExStyle
- ATLWIN/ATL::CWinTraits::GetWndStyle
helpviewer_keywords:
- CMDIChildWinTraits class
- window styles, default values for ATL
- CWinTraits class
- CFrameWinTraits class
- CControlWinTraits class
ms.assetid: f78f486e-6d9c-42c6-8e86-371e05aa7e59
ms.openlocfilehash: 3f23342cae58d70a602ebce1dcbe7efcddf36781
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140089"
---
# <a name="cwintraits-class"></a>CWinTraits クラス

このクラスは、ウィンドウオブジェクトの作成時に使用されるスタイルを標準化するためのメソッドを提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <DWORD t_dwStyle = 0, DWORD t_dwExStyle = 0>  class CWinTraits
```

#### <a name="parameters"></a>パラメーター

*t_dwStyle*<br/>
既定の標準ウィンドウスタイル。

*t_dwExStyle*<br/>
既定の拡張ウィンドウスタイル。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CWinTraits::GetWndExStyle](#getwndexstyle)|雑音オブジェクトの拡張スタイルを取得し `CWinTraits` ます。|
|[CWinTraits::GetWndStyle](#getwndstyle)|雑音オブジェクトの標準スタイルを取得し `CWinTraits` ます。|

## <a name="remarks"></a>解説

この [ウィンドウの特徴](../../atl/understanding-window-traits.md) クラスは、ATL ウィンドウオブジェクトの作成に使用されるスタイルを標準化するための簡単な方法を提供します。 このクラスの特殊化を、そのウィンドウクラスのインスタンスに使用される既定の標準スタイルと拡張スタイルを指定するために、このクラスのテンプレートパラメーターとして [、または](../../atl/reference/cwindowimpl-class.md) 他の ATL のウィンドウクラスのテンプレートパラメーターとして使用します。

このテンプレートは、 [CWindowImpl:: Create](../../atl/reference/cwindowimpl-class.md#create)の呼び出しで他のスタイルが指定されていない場合にのみ使用される既定のウィンドウスタイルを提供するときに使用します。

ATL では、一般的に使用されるウィンドウスタイルの組み合わせに対して、このテンプレートの3つの定義済みの特殊化が提供されます。

- `CControlWinTraits`

   標準コントロールウィンドウ用に設計されています。 WS_CHILD、WS_VISIBLE、WS_CLIPCHILDREN、および WS_CLIPSIBLINGS の標準スタイルが使用されます。 拡張スタイルはありません。

- `CFrameWinTraits`

   標準のフレームウィンドウ用に設計されています。 使用される標準スタイルには、WS_OVERLAPPEDWINDOW、WS_CLIPCHILDREN、および WS_CLIPSIBLINGS があります。 使用される拡張スタイルには、WS_EX_APPWINDOW と WS_EX_WINDOWEDGE があります。

- `CMDIChildWinTraits`

   標準的な MDI 子ウィンドウ用に設計されています。 使用される標準スタイルには、WS_OVERLAPPEDWINDOW、WS_CHILD、WS_VISIBLE、WS_CLIPCHILDREN、および WS_CLIPSIBLINGS があります。 使用される拡張スタイルには、WS_EX_MDICHILD があります。

特定のスタイルがウィンドウクラスのすべてのインスタンスに対して設定されていることを確認し、インスタンスごとに他のスタイルを設定することを許可する場合は、代わりに [CWinTraitsOR](../../atl/reference/cwintraitsor-class.md) を使用します。

## <a name="requirements"></a>要件

**ヘッダー:** atlwin. h

## <a name="cwintraitsgetwndstyle"></a><a name="getwndstyle"></a> CWinTraits::GetWndStyle

この関数を呼び出して、オブジェクトの標準スタイルを取得し `CWinTraits` ます。

```
static DWORD GetWndStyle(DWORD dwStyle);
```

### <a name="parameters"></a>パラメーター

*dwStyle*<br/>
ウィンドウの作成に使用される標準スタイル。 *DwStyle* が0の場合、テンプレートのスタイル値 ( `t_dwStyle` ) が返されます。 *DwStyle* が0以外の場合、 *dwStyle* が返されます。

### <a name="return-value"></a>戻り値

オブジェクトの標準ウィンドウスタイル。

## <a name="cwintraitsgetwndexstyle"></a><a name="getwndexstyle"></a> CWinTraits::GetWndExStyle

この関数を呼び出して、オブジェクトの拡張スタイルを取得し `CWinTraits` ます。

```
static DWORD GetWndExStyle(DWORD dwExStyle);
```

### <a name="parameters"></a>パラメーター

*dwExStyle*<br/>
ウィンドウの作成に使用される拡張スタイル。 *Dwexstyle* が0の場合、テンプレートのスタイル値 ( `t_dwExStyle` ) が返されます。 *Dwexstyle* が0以外の場合は、 *dwexstyle* が返されます。

### <a name="return-value"></a>戻り値

オブジェクトの拡張ウィンドウスタイル。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)<br/>
[ウィンドウの特徴について](../../atl/understanding-window-traits.md)
