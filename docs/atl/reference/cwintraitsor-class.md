---
title: クウィントレイトソークラス
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
ms.openlocfilehash: 825f79190c6f68cd1372154e4e02f430f545aa48
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330282"
---
# <a name="cwintraitsor-class"></a>クウィントレイトソークラス

このクラスは、ウィンドウ オブジェクトの作成時に使用するスタイルを標準化するためのメソッドを提供します。

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
既定のウィンドウ スタイル。

*t_dwExStyle*<br/>
既定の拡張ウィンドウ スタイル。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[クウィントクレストレーター::ゲットンデックススタイル](#getwndexstyle)|オブジェクトの拡張スタイルを`CWinTraitsOR`取得します。|
|[クウィントレイトソー::ゲットンスタイル](#getwndstyle)|オブジェクトの標準スタイルを`CWinTraitsOR`取得します。|

## <a name="remarks"></a>解説

この[ウィンドウの特徴クラスは](../../atl/understanding-window-traits.md)、ATL ウィンドウ オブジェクトの作成に使用されるスタイルを標準化するための簡単なメソッドを提供します。 このクラスの特殊化を[CWindowImpl](../../atl/reference/cwindowimpl-class.md)または ATL の別のウィンドウ クラスのテンプレート パラメーターとして使用して、そのウィンドウ クラスのインスタンスに使用する標準スタイルと拡張スタイルの最小セットを指定します。

[CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create)の呼び出しでインスタンスごとに設定する他のスタイルを許可しながら、ウィンドウ クラスのすべてのインスタンスに特定のスタイルを確実に設定する場合は、このテンプレートの特殊化を使用します。

呼び出しで他のスタイルが指定されていない場合にのみ使用される既定のウィンドウ スタイルを提供する`CWindowImpl::Create`場合は、代わりに[CWinTraits を](../../atl/reference/cwintraits-class.md)使用します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="cwintraitsorgetwndstyle"></a><a name="getwndstyle"></a>クウィントレイトソー::ゲットンスタイル

`CWinTraits`オブジェクトの標準スタイルと、 で指定された既定のスタイルの組み合わせを取得します ( 論理 OR 演算子を使用して ) *t_dwStyle。*

```
static DWORD GetWndStyle(DWORD dwStyle);
```

### <a name="parameters"></a>パラメーター

*Dwstyle*<br/>
ウィンドウの作成に使用するスタイル。

### <a name="return-value"></a>戻り値

*dwStyle*で渡されるスタイルと、論理 OR 演算子を使用`t_dwStyle`して で指定された既定のスタイルの組み合わせ。

## <a name="cwintraitsorgetwndexstyle"></a><a name="getwndexstyle"></a>クウィントクレストレーター::ゲットンデックススタイル

オブジェクトの拡張スタイルとで指定された既定のスタイル`CWinTraits`の組み合わせを取得します ( 論理 OR 演算子を`t_dwStyle`使用して) を取得します。

```
static DWORD GetWndExStyle(DWORD dwExStyle);
```

### <a name="parameters"></a>パラメーター

*ドウェエクススタイル*<br/>
ウィンドウの作成に使用される拡張スタイル。

### <a name="return-value"></a>戻り値

*dwExStyle*で渡される拡張スタイルと、論理 OR 演算子を`t_dwExStyle`使用して 指定されたデフォルトのスタイルの組み合わせ

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)<br/>
[ウィンドウの特徴について](../../atl/understanding-window-traits.md)
