---
title: CWinTraits クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CWinTraits
- ATLWIN/ATL::CWinTraits
- ATLWIN/ATL::CWinTraits::GetWndExStyle
- ATLWIN/ATL::CWinTraits::GetWndStyle
dev_langs:
- C++
helpviewer_keywords:
- CMDIChildWinTraits class
- window styles, default values for ATL
- CWinTraits class
- CFrameWinTraits class
- CControlWinTraits class
ms.assetid: f78f486e-6d9c-42c6-8e86-371e05aa7e59
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 69ea4cf411e0ded0f1c324cea439d5a5a4c0c553
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50062471"
---
# <a name="cwintraits-class"></a>CWinTraits クラス

このクラスは、ウィンドウ オブジェクトを作成するときに使用するスタイルを標準化するためのメソッドを提供します。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <DWORD t_dwStyle = 0, DWORD t_dwExStyle = 0>  class CWinTraits
```

#### <a name="parameters"></a>パラメーター

*t_dwStyle*<br/>
既定の標準のウィンドウ スタイル。

*t_dwExStyle*<br/>
既定の拡張ウィンドウ スタイル。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CWinTraits::GetWndExStyle](#getwndexstyle)|(静的)拡張スタイルを取得、`CWinTraits`オブジェクト。|
|[CWinTraits::GetWndStyle](#getwndstyle)|(静的)標準のスタイルを取得、`CWinTraits`オブジェクト。|

## <a name="remarks"></a>Remarks

これは、[ウィンドウの特徴](../../atl/understanding-window-traits.md)クラスには、ATL ウィンドウ オブジェクトを作成するために使用するスタイルを標準化するための単純なメソッドが用意されています。 このクラスの特殊化を使用して、テンプレートのパラメーターとして[CWindowImpl](../../atl/reference/cwindowimpl-class.md)で使用される既定の標準および拡張スタイルを指定する ATL のウィンドウ クラスのもう 1 つまたはそのウィンドウ クラスのインスタンス。

既定の呼び出しでその他のスタイルが指定されていない場合にのみ使用されるウィンドウのスタイルを指定する場合に、このテンプレートを使用して[CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create)します。

ATL では、このテンプレートをウィンドウ スタイルの一般的に使用される組み合わせの 3 つ定義済みの特殊化を提供します。

- `CControlWinTraits`

   標準コントロール ウィンドウの設計されています。 次の標準的なスタイルを使用: WS_CHILD、WS_VISIBLE、WS_CLIPCHILDREN、および WS_CLIPSIBLINGS します。 拡張スタイルはありません。

- `CFrameWinTraits`

   標準のフレーム ウィンドウの設計されています。 使用される標準のスタイルが含まれます: WS_OVERLAPPEDWINDOW、WS_CLIPCHILDREN、および WS_CLIPSIBLINGS します。 使用する拡張スタイルが含まれます: WS_EX_APPWINDOW と WS_EX_WINDOWEDGE します。

- `CMDIChildWinTraits`

   標準の MDI 子ウィンドウに設計されています。 使用される標準のスタイルが含まれます: WS_OVERLAPPEDWINDOW、WS_CHILD、WS_VISIBLE、WS_CLIPCHILDREN、および WS_CLIPSIBLINGS します。 使用する拡張スタイルが含まれます: WS_EX_MDICHILD します。

インスタンスごとに設定するには、その他のスタイルを許容しつつ、ウィンドウ クラスのすべてのインスタンスを使用して、特定のスタイルが設定されていることを確認する場合[CWinTraitsOR](../../atl/reference/cwintraitsor-class.md)代わりにします。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

##  <a name="getwndstyle"></a>  CWinTraits::GetWndStyle

標準的なスタイルを取得するには、この関数を呼び出して、`CWinTraits`オブジェクト。

```
static DWORD GetWndStyle(DWORD dwStyle);
```

### <a name="parameters"></a>パラメーター

*dwStyle*<br/>
標準的なスタイルのウィンドウの作成に使用します。 場合*dwStyle*が 0 の場合、テンプレートのスタイル値 (`t_dwStyle`) が返されます。 場合*dwStyle* 0 以外の場合、 *dwStyle*が返されます。

### <a name="return-value"></a>戻り値

オブジェクトの標準のウィンドウ スタイル。

##  <a name="getwndexstyle"></a>  CWinTraits::GetWndExStyle

拡張スタイルを取得するには、この関数を呼び出して、`CWinTraits`オブジェクト。

```
static DWORD GetWndExStyle(DWORD dwExStyle);
```

### <a name="parameters"></a>パラメーター

*dwExStyle*<br/>
拡張スタイルのウィンドウの作成に使用します。 場合*dwExStyle*が 0 の場合、テンプレートのスタイル値 (`t_dwExStyle`) が返されます。 場合*dwExStyle* 0 以外の場合、 *dwExStyle*が返されます。

### <a name="return-value"></a>戻り値

オブジェクトの拡張ウィンドウ スタイル。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)<br/>
[ウィンドウの特徴を理解する](../../atl/understanding-window-traits.md)
