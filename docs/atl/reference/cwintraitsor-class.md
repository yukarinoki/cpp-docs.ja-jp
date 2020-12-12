---
description: '詳細情報: CWinTraitsOR クラス'
title: CWinTraitsOR クラス
ms.date: 11/04/2016
f1_keywords:
- CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR::GetWndExStyle
- ATLWIN/ATL::CWinTraitsOR::GetWndStyle
helpviewer_keywords:
- CWinTraitsOR class
- window styles, default values for ATL
ms.assetid: 1eb7b1e8-a9bd-411b-a30a-35a8a10af989
ms.openlocfilehash: 1d0a7ff8a78ebbdc416bdace2a1ea1f0199c292f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140063"
---
# <a name="cwintraitsor-class"></a>CWinTraitsOR クラス

このクラスは、ウィンドウオブジェクトの作成時に使用されるスタイルを標準化するためのメソッドを提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <DWORD t_dwStyle = 0,
          DWORD t_dwExStyle = 0,
          class TWinTraits = CControlWinTraits>
class CWinTraitsOR
```

#### <a name="parameters"></a>パラメーター

*t_dwStyle*<br/>
既定のウィンドウスタイル。

*t_dwExStyle*<br/>
既定の拡張ウィンドウスタイル。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CWinTraitsOR::GetWndExStyle](#getwndexstyle)|オブジェクトの拡張スタイルを取得し `CWinTraitsOR` ます。|
|[CWinTraitsOR::GetWndStyle](#getwndstyle)|オブジェクトの標準スタイルを取得し `CWinTraitsOR` ます。|

## <a name="remarks"></a>解説

この [ウィンドウの特徴](../../atl/understanding-window-traits.md) クラスは、ATL ウィンドウオブジェクトの作成に使用されるスタイルを標準化するための簡単な方法を提供します。 このクラスの特殊化を、そのウィンドウクラスのインスタンスに使用される標準スタイルと拡張スタイルの最小セットを指定するために、このクラスのテンプレートパラメーターとして、その他の [ATL または](../../atl/reference/cwindowimpl-class.md) ATL のウィンドウクラスに使用します。

特定のスタイルがウィンドウクラスのすべてのインスタンスに対して設定されていることを確認し、 [CWindowImpl:: Create](../../atl/reference/cwindowimpl-class.md#create)の呼び出しでインスタンスごとに他のスタイルを設定することを許可する場合は、このテンプレートの特殊化を使用します。

の呼び出しで他のスタイルが指定されていない場合にのみ使用される既定のウィンドウスタイルを指定するには `CWindowImpl::Create` 、代わりに [CWinTraits](../../atl/reference/cwintraits-class.md) を使用します。

## <a name="requirements"></a>要件

**ヘッダー:** atlwin. h

## <a name="cwintraitsorgetwndstyle"></a><a name="getwndstyle"></a> CWinTraitsOR::GetWndStyle

オブジェクトの標準スタイル `CWinTraits` と *t_dwStyle* によって指定された既定のスタイルの組み合わせ (論理 OR 演算子を使用) を取得するには、この関数を呼び出します。

```
static DWORD GetWndStyle(DWORD dwStyle);
```

### <a name="parameters"></a>パラメーター

*dwStyle*<br/>
ウィンドウの作成に使用されるスタイル。

### <a name="return-value"></a>戻り値

*DwStyle* で渡されるスタイルと、によって指定された既定値の組み合わせ。 `t_dwStyle` 論理 OR 演算子を使用します。

## <a name="cwintraitsorgetwndexstyle"></a><a name="getwndexstyle"></a> CWinTraitsOR::GetWndExStyle

オブジェクトの拡張スタイル `CWinTraits` とで指定された既定のスタイルの組み合わせ (論理 OR 演算子を使用) を取得するには、この関数を呼び出し `t_dwStyle` ます。

```
static DWORD GetWndExStyle(DWORD dwExStyle);
```

### <a name="parameters"></a>パラメーター

*dwExStyle*<br/>
ウィンドウの作成に使用される拡張スタイル。

### <a name="return-value"></a>戻り値

*Dwexstyle* で渡される拡張スタイルと、によって指定された既定のスタイルの組み合わせ `t_dwExStyle` (論理 OR 演算子を使用)

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)<br/>
[ウィンドウの特徴について](../../atl/understanding-window-traits.md)
