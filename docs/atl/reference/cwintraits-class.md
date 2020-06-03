---
title: CWinTraitsクラス
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
ms.openlocfilehash: fd73f733e4eff21da92937d1e1b0cce21552a48c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330313"
---
# <a name="cwintraits-class"></a>CWinTraitsクラス

このクラスは、ウィンドウ オブジェクトの作成時に使用するスタイルを標準化するためのメソッドを提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <DWORD t_dwStyle = 0, DWORD t_dwExStyle = 0>  class CWinTraits
```

#### <a name="parameters"></a>パラメーター

*t_dwStyle*<br/>
既定の標準ウィンドウ スタイル。

*t_dwExStyle*<br/>
既定の拡張ウィンドウ スタイル。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[クウィントレイツ::ゲットンデックススタイル](#getwndexstyle)|(静的)オブジェクトの拡張スタイルを`CWinTraits`取得します。|
|[クウィントレイツ::ゲットンスタイル](#getwndstyle)|(静的)オブジェクトの標準スタイルを`CWinTraits`取得します。|

## <a name="remarks"></a>解説

この[ウィンドウの特徴クラスは](../../atl/understanding-window-traits.md)、ATL ウィンドウ オブジェクトの作成に使用されるスタイルを標準化するための簡単なメソッドを提供します。 このクラスの特殊化を[CWindowImpl](../../atl/reference/cwindowimpl-class.md)または ATL の別のウィンドウ クラスのテンプレート パラメーターとして使用して、そのウィンドウ クラスのインスタンスに使用される既定の標準スタイルと拡張スタイルを指定します。

[CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create)の呼び出しで他のスタイルが指定されていない場合にのみ使用される既定のウィンドウ スタイルを提供する場合は、このテンプレートを使用します。

ATL は、一般的に使用されるウィンドウ スタイルの組み合わせに対して、このテンプレートの 3 つの事前定義された特殊化を提供します。

- `CControlWinTraits`

   標準のコントロール ウィンドウ用に設計されています。 WS_CHILD、WS_VISIBLE、WS_CLIPCHILDREN、およびWS_CLIPSIBLINGSの標準スタイルが使用されます。 拡張スタイルはありません。

- `CFrameWinTraits`

   標準フレーム ウィンドウ用に設計されています。 使用される標準スタイルには、WS_OVERLAPPEDWINDOW、WS_CLIPCHILDREN、WS_CLIPSIBLINGSなどがあります。 使用される拡張スタイルには、WS_EX_APPWINDOWとWS_EX_WINDOWEDGEがあります。

- `CMDIChildWinTraits`

   標準 MDI 子ウィンドウ用に設計されています。 使用される標準スタイルには、WS_OVERLAPPEDWINDOW、WS_CHILD、WS_VISIBLE、WS_CLIPCHILDREN、WS_CLIPSIBLINGSがあります。 使用される拡張スタイルには、WS_EX_MDICHILDが含まれます。

特定のスタイルがウィンドウ クラスのすべてのインスタンスに設定され、インスタンスごとに他のスタイルを設定できるようにする場合は[、CWinTraitsOR を](../../atl/reference/cwintraitsor-class.md)代わりに使用します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="cwintraitsgetwndstyle"></a><a name="getwndstyle"></a>クウィントレイツ::ゲットンスタイル

`CWinTraits`オブジェクトの標準スタイルを取得します。

```
static DWORD GetWndStyle(DWORD dwStyle);
```

### <a name="parameters"></a>パラメーター

*Dwstyle*<br/>
ウィンドウの作成に使用される標準スタイル。 *dwStyle*が 0 の場合、テンプレート`t_dwStyle`スタイル値 ( ) が返されます。 *dwStyle*が 0 以外の場合は *、dwStyle*が返されます。

### <a name="return-value"></a>戻り値

オブジェクトの標準ウィンドウ スタイル。

## <a name="cwintraitsgetwndexstyle"></a><a name="getwndexstyle"></a>クウィントレイツ::ゲットンデックススタイル

`CWinTraits`オブジェクトの拡張スタイルを取得します。

```
static DWORD GetWndExStyle(DWORD dwExStyle);
```

### <a name="parameters"></a>パラメーター

*ドウェエクススタイル*<br/>
ウィンドウの作成に使用される拡張スタイル。 *dwExStyle*が 0 の場合、テンプレート`t_dwExStyle`スタイル値 ( ) が返されます。 *dwExStyle*が 0 以外の場合は *、dwExStyle*が返されます。

### <a name="return-value"></a>戻り値

オブジェクトの拡張ウィンドウ スタイル。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)<br/>
[ウィンドウの特徴について](../../atl/understanding-window-traits.md)
