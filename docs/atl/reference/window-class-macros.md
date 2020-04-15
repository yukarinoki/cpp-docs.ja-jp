---
title: ウィンドウ クラス マクロ
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::DECLARE_WND_CLASS
- atlwin/ATL::DECLARE_WND_SUPERCLASS
- atlwin/ATL::DECLARE_WND_CLASS_EX
ms.assetid: ce18681a-2bab-4453-9895-0f3ea47c2b24
ms.openlocfilehash: 18c0912c506bc52421b18d36346204b557c0fc5c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325725"
---
# <a name="window-class-macros"></a>ウィンドウ クラス マクロ

これらのマクロは、ウィンドウ クラス ユーティリティを定義します。

|||
|-|-|
|[DECLARE_WND_CLASS](#declare_wnd_class)|新しいウィンドウ クラスの名前を指定できます。|
|[DECLARE_WND_CLASS2](#declare_wnd_class2)|(ビジュアルスタジオ2017)新しいウィンドウ クラスの名前と、新しいクラスが使用するウィンドウ プロシージャを含む外側のクラスを指定できます。|
|[DECLARE_WND_SUPERCLASS](#declare_wnd_superclass)|新しいウィンドウ クラスの基になる既存のウィンドウ クラスの名前を指定できます。|
|[DECLARE_WND_CLASS_EX](#declare_wnd_class_ex)|クラスのパラメータを指定できます。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="declare_wnd_class"></a><a name="declare_wnd_class"></a>DECLARE_WND_CLASS

新しいウィンドウ クラスの名前を指定できます。 このマクロを ATL ActiveX コントロールのコントロール クラスに配置します。

```
DECLARE_WND_CLASS( WndClassName )
```

### <a name="parameters"></a>パラメーター

*クラス名*<br/>
[in]新しいウィンドウ クラスの名前。 NULL の場合、ATL はウィンドウ クラス名を生成します。

### <a name="remarks"></a>解説

/permissive- コンパイラ オプションを使用している場合、DECLARE_WND_CLASSコンパイラ エラーが発生します。代わりにDECLARE_WND_CLASS2を使用します。

DECLARE_WND_CLASSを使用すると、情報が[CWndClassInfo](cwndclassinfo-class.md)によって管理される新しいウィンドウ クラスの名前を指定できます。 DECLARE_WND_CLASSは、次の静的関数を実装することによって、新しいウィンドウ クラスを定義します。

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

DECLARE_WND_CLASSは、新しいウィンドウに次のスタイルを指定します。

- CS_HREDRAW

- CS_VREDRAW

- CS_DBLCLKS

DECLARE_WND_CLASSは、既定のウィンドウの背景色も指定します。 [DECLARE_WND_CLASS_EX](#declare_wnd_class_ex)マクロを使用して、独自のスタイルと背景色を指定します。

[CWindowImpl](cwindowimpl-class.md)は、DECLARE_WND_CLASS マクロを使用して、新しいウィンドウ クラスに基づいてウィンドウを作成します。 この動作をオーバーライドするには[、DECLARE_WND_SUPERCLASS](#declare_wnd_superclass)マクロを使用するか、[または GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo)関数の独自の実装を提供します。

ATL でのウィンドウの使用の詳細については[、「ATL ウィンドウ クラス](../../atl/atl-window-classes.md)」を参照してください。

## <a name="declare_wnd_class2"></a><a name="declare_wnd_class2"></a>DECLARE_WND_CLASS2

(ビジュアルスタジオ2017)DECLARE_WND_CLASSに似ていますが、/permissive- オプションを指定してコンパイルするときに、依存名エラーを回避する追加のパラメーターを使用します。

```
DECLARE_WND_CLASS2( WndClassName, EnclosingClass )
```

### <a name="parameters"></a>パラメーター

*クラス名*<br/>
[in]新しいウィンドウ クラスの名前。 NULL の場合、ATL はウィンドウ クラス名を生成します。

*クラスを囲む*<br/>
[in]新しいウィンドウ クラスを囲むウィンドウ クラスの名前。 Nll は指定できません。

### <a name="remarks"></a>解説

/permissive オプションを使用している場合、DECLARE_WND_CLASS依存名が含まれているためコンパイル エラーが発生します。 DECLARE_WND_CLASS2このマクロが使用されているクラスに明示的に名前を付ける必要があり、/permissive-フラグの下でエラーが発生することはありません。
それ以外の場合、このマクロは[DECLARE_WND_CLASS](#declare_wnd_class)と同一です。

## <a name="declare_wnd_superclass"></a><a name="declare_wnd_superclass"></a>DECLARE_WND_SUPERCLASS

クラスのパラメータを指定できます。 このマクロを ATL ActiveX コントロールのコントロール クラスに配置します。

```
DECLARE_WND_SUPERCLASS( WndClassName, OrigWndClassName )
```

### <a name="parameters"></a>パラメーター

*クラス名*<br/>
[in]スーパークラスを指定するウィンドウ クラスの*名前*。 NULL の場合、ATL はウィンドウ クラス名を生成します。

*オリグウンドクラス名*<br/>
[in]既存のウィンドウ クラスの名前。

### <a name="remarks"></a>解説

このマクロを使用すると、既存のウィンドウ クラスをスーパークラス化するウィンドウ クラスの名前を指定できます。 [CWndClassInfo は](cwndclassinfo-class.md)、スーパークラスの情報を管理します。

DECLARE_WND_SUPERCLASSは、次の静的関数を実装します。

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

既定では[、CWindowImpl](cwindowimpl-class.md)は[、新](#declare_wnd_class)しいウィンドウ クラスに基づいてウィンドウを作成するDECLARE_WND_CLASS マクロを使用します。 派生クラスでDECLARE_WND_SUPERCLASSマクロを`CWindowImpl`指定すると、ウィンドウ クラスは既存のクラスに基づいていますが、ウィンドウ プロシージャを使用します。 この手法はスーパークラス化と呼ばれます。

DECLARE_WND_CLASSとDECLARE_WND_SUPERCLASSマクロを使用する以外に、独自の実装で[GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo)関数をオーバーライドできます。

ATL でのウィンドウの使用の詳細については[、「ATL ウィンドウ クラス](../../atl/atl-window-classes.md)」を参照してください。

## <a name="declare_wnd_class_ex"></a><a name="declare_wnd_class_ex"></a>DECLARE_WND_CLASS_EX

新しいウィンドウ クラスの基になる既存のウィンドウ クラスの名前を指定できます。 このマクロを ATL ActiveX コントロールのコントロール クラスに配置します。

```
DECLARE_WND_CLASS_EX( WndClassName, style, bkgnd )
```

### <a name="parameters"></a>パラメーター

*クラス名*<br/>
[in]新しいウィンドウ クラスの名前。 NULL の場合、ATL はウィンドウ クラス名を生成します。

*スタイル*<br/>
[in]ウィンドウのスタイル。

*bkgnd*<br/>
[in]ウィンドウの背景色。

### <a name="remarks"></a>解説

このマクロを使用すると、[新](cwndclassinfo-class.md)しいウィンドウ クラスのクラス パラメータを指定できます。 DECLARE_WND_CLASS_EX、次の静的関数を実装することによって、新しいウィンドウ クラスを定義します。

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

既定のスタイルと背景色を使用する場合は[、DECLARE_WND_CLASS](#declare_wnd_class)マクロを使用します。 ATL でのウィンドウの使用の詳細については[、「ATL ウィンドウ クラス](../../atl/atl-window-classes.md)」を参照してください。

## <a name="see-also"></a>関連項目

[マクロ](atl-macros.md)
