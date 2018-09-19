---
title: CWinTraitsOR クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR::GetWndExStyle
- ATLWIN/ATL::CWinTraitsOR::GetWndStyle
dev_langs:
- C++
helpviewer_keywords:
- CWinTraitsOR class
- window styles, default values for ATL
ms.assetid: 1eb7b1e8-a9bd-411b-a30a-35a8a10af989
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 48303c6115ac1d2314e3038556b8f98330a6182e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062671"
---
# <a name="cwintraitsor-class"></a>CWinTraitsOR クラス

このクラスは、ウィンドウ オブジェクトを作成するときに使用するスタイルを標準化するためのメソッドを提供します。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

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
|[CWinTraitsOR::GetWndExStyle](#getwndexstyle)|拡張スタイルを取得、`CWinTraitsOR`オブジェクト。|
|[CWinTraitsOR::GetWndStyle](#getwndstyle)|標準のスタイルを取得、`CWinTraitsOR`オブジェクト。|

## <a name="remarks"></a>Remarks

これは、[ウィンドウの特徴](../../atl/understanding-window-traits.md)クラスには、ATL ウィンドウ オブジェクトを作成するために使用するスタイルを標準化するための単純なメソッドが用意されています。 このクラスの特殊化を使用して、テンプレートのパラメーターとして[CWindowImpl](../../atl/reference/cwindowimpl-class.md)に使用される標準および拡張スタイルの最小セットを指定する ATL のウィンドウ クラスのもう 1 つまたはそのウィンドウ クラスのインスタンス。

特定のスタイル設定されているウィンドウ クラスのすべてのインスタンスの他のスタイルを許容しつつへの呼び出しで、インスタンスごとに設定することを確認する場合は、このテンプレートの特殊化を使用して[CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create)します。

既定の呼び出しでその他のスタイルが指定されていない場合にのみ使用されるウィンドウのスタイルを指定する場合`CWindowImpl::Create`を使用して、 [CWinTraits](../../atl/reference/cwintraits-class.md)代わりにします。

## <a name="requirements"></a>要件

**ヘッダー:** atlwin.h

##  <a name="getwndstyle"></a>  CWinTraitsOR::GetWndStyle

(論理 OR 演算子を使用して) の標準的なスタイルの組み合わせを取得するには、この関数を呼び出して、`CWinTraits`オブジェクトと既定のスタイルで指定された*t_dwStyle*します。

```
static DWORD GetWndStyle(DWORD dwStyle);
```

### <a name="parameters"></a>パラメーター

*dwStyle*<br/>
スタイルのウィンドウの作成に使用します。

### <a name="return-value"></a>戻り値

渡されるスタイルの組み合わせ*dwStyle*と既定値で指定されたもの`t_dwStyle`、論理 OR 演算子を使用します。

##  <a name="getwndexstyle"></a>  CWinTraitsOR::GetWndExStyle

(論理 OR 演算子を使用して) の拡張スタイルの組み合わせを取得するには、この関数を呼び出して、`CWinTraits`オブジェクトと既定のスタイルで指定された`t_dwStyle`します。

```
static DWORD GetWndExStyle(DWORD dwExStyle);
```

### <a name="parameters"></a>パラメーター

*dwExStyle*<br/>
拡張スタイルのウィンドウの作成に使用します。

### <a name="return-value"></a>戻り値

渡される拡張スタイルを組み合わせた*dwExStyle*であり、既定で指定されたもの`t_dwExStyle`、論理 OR 演算子を使用します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)<br/>
[ウィンドウの特徴を理解する](../../atl/understanding-window-traits.md)

