---
description: '詳細情報: CWndClassInfo クラス'
title: CWndClassInfo クラス
ms.date: 11/04/2016
f1_keywords:
- CWndClassInfo
- ATLWIN/ATL::CWndClassInfo
- ATLWIN/ATL::Register
- ATLWIN/ATL::m_atom
- ATLWIN/ATL::m_bSystemCursor
- ATLWIN/ATL::m_lpszCursorID
- ATLWIN/ATL::m_lpszOrigName
- ATLWIN/ATL::m_szAutoName
- ATLWIN/ATL::m_wc
- ATLWIN/ATL::pWndProc
helpviewer_keywords:
- CWndClassInfo class
ms.assetid: c36fe7e1-75f1-4cf5-a06f-9f59c43fe6fb
ms.openlocfilehash: 7a857812fa35743fbab0968fb94095bf8fdcabcf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140024"
---
# <a name="cwndclassinfo-class"></a>CWndClassInfo クラス

このクラスには、ウィンドウクラスの情報を登録するためのメソッドが用意されています。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CWndClassInfo
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|-|-|
|[[登録]](#register)|ウィンドウクラスを登録します。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|-|-|
|[m_atom](#m_atom)|登録されたウィンドウクラスを一意に識別します。|
|[m_bSystemCursor](#m_bsystemcursor)|カーソルリソースがシステムカーソルを参照するのか、またはモジュールリソースに含まれるカーソルを参照するのかを指定します。|
|[m_lpszCursorID](#m_lpszcursorid)|カーソルリソースの名前を指定します。|
|[m_lpszOrigName](#m_lpszorigname)|既存のウィンドウクラスの名前を格納します。|
|[m_szAutoName](#m_szautoname)|ウィンドウクラスの ATL によって生成された名前を保持します。|
|[m_wc](#m_wc)|ウィンドウクラス情報を `WNDCLASSEX` 構造体に保持します。|
|[pWndProc](#pwndproc)|既存のウィンドウクラスのウィンドウプロシージャを指します。|

## <a name="remarks"></a>解説

`CWndClassInfo` ウィンドウクラスの情報を管理します。 通常、 `CWndClassInfo` 次の表に示すように、DECLARE_WND_CLASS、DECLARE_WND_CLASS_EX、または DECLARE_WND_SUPERCLASS の3つのマクロのいずれかを使用してを使用します。

|マクロ|説明|
|-----------|-----------------|
|[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)|`CWndClassInfo` 新しいウィンドウクラスの情報を登録します。|
|[DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex)|`CWndClassInfo` クラスパラメーターを含む新しいウィンドウクラスの情報を登録します。|
|[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)|`CWndClassInfo` 既存のクラスに基づいていて、別のウィンドウプロシージャを使用するウィンドウクラスの情報を登録します。 この手法は superclassing と呼ばれます。|

既定では、 [CWindowImpl](../../atl/reference/cwindowimpl-class.md) には、 `DECLARE_WND_CLASS` 新しいウィンドウクラスに基づいてウィンドウを作成するマクロが含まれています。 DECLARE_WND_CLASS には、コントロールの既定のスタイルと背景色が用意されています。 スタイルと背景色を自分で指定する場合は、からクラスを派生させ、 `CWindowImpl` クラス定義に DECLARE_WND_CLASS_EX マクロを含めます。

既存のウィンドウクラスに基づいてウィンドウを作成する場合は、からクラスを派生させ、 `CWindowImpl` DECLARE_WND_SUPERCLASS マクロをクラス定義に含めます。 次に例を示します。

[!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwndclassinfo-class_1.h)]

ウィンドウクラスの詳細については、「Windows SDK の [ウィンドウクラス](/windows/win32/winmsg/window-classes) 」を参照してください。

ATL で windows を使用する方法の詳細については、「 [Atl ウィンドウクラス](../../atl/atl-window-classes.md)」を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** atlwin. h

## <a name="cwndclassinfom_atom"></a><a name="m_atom"></a> CWndClassInfo:: m_atom

登録されているウィンドウクラスの一意の識別子を格納します。

```
ATOM m_atom;
```

## <a name="cwndclassinfom_bsystemcursor"></a><a name="m_bsystemcursor"></a> CWndClassInfo:: m_bSystemCursor

TRUE の場合、ウィンドウクラスが登録されるときにシステムカーソルリソースが読み込まれます。

```
BOOL m_bSystemCursor;
```

### <a name="remarks"></a>解説

それ以外の場合は、モジュールに含まれるカーソルリソースが読み込まれます。

`CWndClassInfo``m_bSystemCursor` [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) ( [CWindowImpl](../../atl/reference/cwindowimpl-class.md)の既定値) または[DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex)マクロが指定されている場合にのみを使用します。 この場合、 `m_bSystemCursor` は TRUE に初期化されます。 詳細については、「 [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) の概要」を参照してください。

## <a name="cwndclassinfom_lpszcursorid"></a><a name="m_lpszcursorid"></a> CWndClassInfo:: m_lpszCursorID

カーソルリソースの名前、または下位ワードのリソース識別子を指定します。上位ワードの場合は、0を指定します。

```
LPCTSTR m_lpszCursorID;
```

### <a name="remarks"></a>解説

ウィンドウクラスが登録されると、によって識別されるカーソルへのハンドルが取得され、 `m_lpszCursorID` [m_wc](#m_wc)によって格納されます。

`CWndClassInfo``m_lpszCursorID` [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) ( [CWindowImpl](../../atl/reference/cwindowimpl-class.md)の既定値) または[DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex)マクロが指定されている場合にのみを使用します。 この場合、 `m_lpszCursorID` は IDC_ARROW に初期化されます。 詳細については、「 [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) の概要」を参照してください。

## <a name="cwndclassinfom_lpszorigname"></a><a name="m_lpszorigname"></a> CWndClassInfo:: m_lpszOrigName

既存のウィンドウクラスの名前を格納します。

```
LPCTSTR m_lpszOrigName;
```

### <a name="remarks"></a>解説

`CWndClassInfo``m_lpszOrigName`クラス定義に[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)マクロを含める場合にのみ、を使用します。 この場合、は、 `CWndClassInfo` によって指定されたクラスに基づいてウィンドウクラスを登録 `m_lpszOrigName` します。 詳細については、「 [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) の概要」を参照してください。

## <a name="cwndclassinfom_szautoname"></a><a name="m_szautoname"></a> CWndClassInfo:: m_szAutoName

ウィンドウクラスの名前を保持します。

```
TCHAR m_szAutoName[13];
```

### <a name="remarks"></a>解説

`CWndClassInfo``m_szAutoName` `WndClassName` パラメーターの[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)、 [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex)または[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)に NULL が渡された場合にのみ、を使用します。 ウィンドウクラスが登録されると、ATL によって名前が作成されます。

## <a name="cwndclassinfom_wc"></a><a name="m_wc"></a> CWndClassInfo:: m_wc

ウィンドウクラスの情報を [WNDCLASSEX](/windows/win32/api/winuser/ns-winuser-wndclassexw) 構造体に保持します。

```
WNDCLASSEX m_wc;
```

### <a name="remarks"></a>解説

[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) ( [CWindowImpl](../../atl/reference/cwindowimpl-class.md)の既定値) または[DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex)マクロを指定した場合は、 `m_wc` 新しいウィンドウクラスに関する情報が含まれます。

[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)マクロを指定した場合、には、 `m_wc` 既存のクラスに基づくが、別のウィンドウプロシージャを使用するウィンドウクラスである、スーパークラスに関する情報が含まれます。 [m_lpszOrigName](#m_lpszorigname) と [pwndproc](#pwndproc) では、既存のウィンドウクラスの名前とウィンドウプロシージャをそれぞれ保存します。

## <a name="cwndclassinfopwndproc"></a><a name="pwndproc"></a> CWndClassInfo::p WndProc

既存のウィンドウクラスのウィンドウプロシージャを指します。

```
WNDPROC pWndProc;
```

### <a name="remarks"></a>解説

`CWndClassInfo``pWndProc`クラス定義に[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)マクロを含める場合にのみ、を使用します。 この場合、は `CWndClassInfo` 既存のクラスに基づくウィンドウクラスを登録しますが、別のウィンドウプロシージャを使用します。 既存のウィンドウクラスのウィンドウプロシージャは、に保存され `pWndProc` ます。 詳細については、「 [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) の概要」を参照してください。

## <a name="cwndclassinforegister"></a><a name="register"></a> CWndClassInfo:: Register

まだ登録されていない場合にウィンドウクラスを登録するために、 [CWindowImpl:: Create](../../atl/reference/cwindowimpl-class.md#create) によって呼び出されます。

```
ATOM Register(WNDPROC* pProc);
```

### <a name="parameters"></a>パラメーター

*pProc*<br/>
入出力既存のウィンドウクラスの元のウィンドウプロシージャを指定します。

### <a name="return-value"></a>戻り値

成功した場合は、登録されているウィンドウクラスを一意に識別する atom。 それ以外の場合は、0 に設定されます。

### <a name="remarks"></a>解説

[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) ( [CWindowImpl](../../atl/reference/cwindowimpl-class.md)の既定値) または[DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex)マクロを指定した場合は、によって `Register` 新しいウィンドウクラスが登録されます。 この場合、 *Pproc* パラメーターは使用されません。

[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)マクロを指定した場合、は、 `Register` 既存のクラスに基づいているが別のウィンドウプロシージャを使用するウィンドウクラスである、スーパークラスを登録します。 既存のウィンドウクラスのウィンドウプロシージャが *Pproc* に返されます。

## <a name="see-also"></a>関連項目

[CComControl クラス](../../atl/reference/ccomcontrol-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
