---
title: ウィンドウクラスマクロ
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::DECLARE_WND_CLASS
- atlwin/ATL::DECLARE_WND_SUPERCLASS
- atlwin/ATL::DECLARE_WND_CLASS_EX
ms.assetid: ce18681a-2bab-4453-9895-0f3ea47c2b24
ms.openlocfilehash: ca19eba1632ef3754b704c82ad5a872160ae0c91
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834467"
---
# <a name="window-class-macros"></a>ウィンドウクラスマクロ

これらのマクロは、ウィンドウクラスユーティリティを定義します。

|名前|説明|
|-|-|
|[DECLARE_WND_CLASS](#declare_wnd_class)|新しいウィンドウクラスの名前を指定できます。|
|[DECLARE_WND_CLASS2](#declare_wnd_class2)|(Visual Studio 2017)新しいウィンドウクラスの名前と、新しいクラスが使用するウィンドウプロシージャを持つ外側のクラスの名前を指定できます。|
|[DECLARE_WND_SUPERCLASS](#declare_wnd_superclass)|新しいウィンドウクラスの基になる既存のウィンドウクラスの名前を指定できます。|
|[DECLARE_WND_CLASS_EX](#declare_wnd_class_ex)|クラスのパラメーターを指定できます。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlwin. h

## <a name="declare_wnd_class"></a><a name="declare_wnd_class"></a> DECLARE_WND_CLASS

新しいウィンドウクラスの名前を指定できます。 このマクロを ATL ActiveX コントロールのコントロールクラスに配置します。

```
DECLARE_WND_CLASS( WndClassName )
```

### <a name="parameters"></a>パラメーター

*WndClassName*<br/>
から新しいウィンドウクラスの名前。 NULL の場合、ATL はウィンドウクラス名を生成します。

### <a name="remarks"></a>解説

/Permissive-コンパイラオプションを使用している場合、DECLARE_WND_CLASS によってコンパイラエラーが発生します。代わりに DECLARE_WND_CLASS2 を使用してください。

DECLARE_WND_CLASS では、 [CWndClassInfo](cwndclassinfo-class.md)によって管理される情報を持つ新しいウィンドウクラスの名前を指定できます。 DECLARE_WND_CLASS は、次の静的関数を実装することで、新しいウィンドウクラスを定義します。

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

DECLARE_WND_CLASS 新しいウィンドウに次のスタイルを指定します。

- CS_HREDRAW

- CS_VREDRAW

- CS_DBLCLKS

DECLARE_WND_CLASS、既定のウィンドウの背景色も指定します。 [DECLARE_WND_CLASS_EX](#declare_wnd_class_ex)マクロを使用して、独自のスタイルと背景色を指定します。

[CWindowImpl](cwindowimpl-class.md) は、DECLARE_WND_CLASS マクロを使用して、新しいウィンドウクラスに基づいてウィンドウを作成します。 この動作をオーバーライドするには、 [DECLARE_WND_SUPERCLASS](#declare_wnd_superclass) マクロを使用するか、 [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) 関数の独自の実装を指定します。

ATL で windows を使用する方法の詳細については、「 [Atl ウィンドウクラス](../../atl/atl-window-classes.md)」を参照してください。

## <a name="declare_wnd_class2"></a><a name="declare_wnd_class2"></a> DECLARE_WND_CLASS2

(Visual Studio 2017)DECLARE_WND_CLASS に似ていますが、/permissive-オプションを使用してコンパイルするときに、依存する名前のエラーを回避するパラメーターが追加されています。

```
DECLARE_WND_CLASS2( WndClassName, EnclosingClass )
```

### <a name="parameters"></a>パラメーター

*WndClassName*<br/>
から新しいウィンドウクラスの名前。 NULL の場合、ATL はウィンドウクラス名を生成します。

*EnclosingClass*<br/>
から新しいウィンドウクラスを囲むウィンドウクラスの名前。 Nll は指定できません。

### <a name="remarks"></a>解説

/Permissive-オプションを使用している場合は、依存する名前が含まれているため、DECLARE_WND_CLASS によってコンパイルエラーが発生します。 DECLARE_WND_CLASS2 では、このマクロを使用するクラスの名前を明示的に指定する必要があり、/permissive-フラグの下ではエラーは発生しません。
それ以外の場合、このマクロは [DECLARE_WND_CLASS](#declare_wnd_class)と同じです。

## <a name="declare_wnd_superclass"></a><a name="declare_wnd_superclass"></a> DECLARE_WND_SUPERCLASS

クラスのパラメーターを指定できます。 このマクロを ATL ActiveX コントロールのコントロールクラスに配置します。

```
DECLARE_WND_SUPERCLASS( WndClassName, OrigWndClassName )
```

### <a name="parameters"></a>パラメーター

*WndClassName*<br/>
から *OrigWndClassName*をスーパークラスにするウィンドウクラスの名前。 NULL の場合、ATL はウィンドウクラス名を生成します。

*OrigWndClassName*<br/>
から既存のウィンドウクラスの名前。

### <a name="remarks"></a>解説

このマクロを使用すると、既存のウィンドウクラスをスーパークラスにするウィンドウクラスの名前を指定できます。 [CWndClassInfo](cwndclassinfo-class.md) は、スーパークラスの情報を管理します。

DECLARE_WND_SUPERCLASS は、次の静的関数を実装します。

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

既定では、 [CWindowImpl](cwindowimpl-class.md) は [DECLARE_WND_CLASS](#declare_wnd_class) マクロを使用して、新しいウィンドウクラスに基づいてウィンドウを作成します。 派生クラスで DECLARE_WND_SUPERCLASS マクロを指定することにより、 `CWindowImpl` ウィンドウクラスは既存のクラスに基づいて作成されますが、ウィンドウプロシージャが使用されます。 この手法は superclassing と呼ばれます。

DECLARE_WND_CLASS マクロと DECLARE_WND_SUPERCLASS マクロを使用するだけでなく、 [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) 関数を独自の実装でオーバーライドすることもできます。

ATL で windows を使用する方法の詳細については、「 [Atl ウィンドウクラス](../../atl/atl-window-classes.md)」を参照してください。

## <a name="declare_wnd_class_ex"></a><a name="declare_wnd_class_ex"></a> DECLARE_WND_CLASS_EX

新しいウィンドウクラスの基になる既存のウィンドウクラスの名前を指定できます。 このマクロを ATL ActiveX コントロールのコントロールクラスに配置します。

```
DECLARE_WND_CLASS_EX( WndClassName, style, bkgnd )
```

### <a name="parameters"></a>パラメーター

*WndClassName*<br/>
から新しいウィンドウクラスの名前。 NULL の場合、ATL はウィンドウクラス名を生成します。

*style*<br/>
からウィンドウのスタイル。

*背景*<br/>
からウィンドウの背景色。

### <a name="remarks"></a>解説

このマクロを使用すると、新しいウィンドウクラスのクラスパラメーターを指定できます。このクラスの情報は [CWndClassInfo](cwndclassinfo-class.md)によって管理されます。 DECLARE_WND_CLASS_EX は、次の静的関数を実装することで、新しいウィンドウクラスを定義します。

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

既定のスタイルと背景色を使用する場合は、 [DECLARE_WND_CLASS](#declare_wnd_class) マクロを使用します。 ATL で windows を使用する方法の詳細については、「 [Atl ウィンドウクラス](../../atl/atl-window-classes.md)」を参照してください。

## <a name="see-also"></a>関連項目

[[マクロ]](atl-macros.md)
