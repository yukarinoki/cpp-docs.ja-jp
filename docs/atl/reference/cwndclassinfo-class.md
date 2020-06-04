---
title: クラス
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
ms.openlocfilehash: 01706bf61c3b977c28998325ece68724cfbc7452
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330337"
---
# <a name="cwndclassinfo-class"></a>クラス

このクラスは、ウィンドウ クラスの情報を登録するためのメソッドを提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CWndClassInfo
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|||
|-|-|
|[登録](#register)|ウィンドウ クラスを登録します。|

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|[m_atom](#m_atom)|登録されているウィンドウ クラスを一意に識別します。|
|[m_bSystemCursor](#m_bsystemcursor)|カーソル リソースがシステム カーソルを参照するか、モジュール リソースに含まれるカーソルを参照するかを指定します。|
|[m_lpszCursorID](#m_lpszcursorid)|カーソル リソースの名前を指定します。|
|[m_lpszOrigName](#m_lpszorigname)|既存のウィンドウ クラスの名前を格納します。|
|[m_szAutoName](#m_szautoname)|ATL 生成ウィンドウ クラスの名前を保持します。|
|[m_wc](#m_wc)|構造体の中でウィンドウ`WNDCLASSEX`クラス情報を保持します。|
|[を実行します。](#pwndproc)|既存のウィンドウ クラスのウィンドウ プロシージャへのアクセスポイント。|

## <a name="remarks"></a>解説

`CWndClassInfo`は、ウィンドウ クラスの情報を管理します。 通常、次`CWndClassInfo`の表に示すように、DECLARE_WND_CLASS、DECLARE_WND_CLASS_EX、またはDECLARE_WND_SUPERCLASSの 3 つのマクロのいずれかを使用します。

|マクロ|説明|
|-----------|-----------------|
|[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)|`CWndClassInfo`新しいウィンドウ クラスの情報を登録します。|
|[DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex)|`CWndClassInfo`クラスパラメーターを含む新しいウィンドウ クラスの情報を登録します。|
|[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)|`CWndClassInfo`既存のクラスに基づくが、別のウィンドウ プロシージャを使用するウィンドウ クラスの情報を登録します。 この手法はスーパークラス化と呼ばれます。|

既定では[、CWindowImpl](../../atl/reference/cwindowimpl-class.md)には`DECLARE_WND_CLASS`、新しいウィンドウ クラスに基づいてウィンドウを作成するマクロが含まれています。 DECLARE_WND_CLASSコントロールの既定のスタイルと背景色を提供します。 スタイルと背景色を自分で指定する場合は、クラスを派生`CWindowImpl`させ、DECLARE_WND_CLASS_EXマクロをクラス定義に含めます。

既存のウィンドウ クラスに基づいてウィンドウを作成する場合は、クラスを派生`CWindowImpl`し、クラス定義にDECLARE_WND_SUPERCLASS マクロを含めます。 次に例を示します。

[!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwndclassinfo-class_1.h)]

ウィンドウ クラスの詳細については、「Windows SDK の[ウィンドウ クラス](/windows/win32/winmsg/window-classes)」を参照してください。

ATL でのウィンドウの使用の詳細については[、「ATL ウィンドウ クラス](../../atl/atl-window-classes.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="cwndclassinfom_atom"></a><a name="m_atom"></a>クーンドクラス情報::m_atom

登録されたウィンドウ クラスの一意の識別子を格納します。

```
ATOM m_atom;
```

## <a name="cwndclassinfom_bsystemcursor"></a><a name="m_bsystemcursor"></a>クラス情報::m_bSystemCursor

TRUE の場合、ウィンドウ クラスが登録されると、システム カーソル リソースが読み込まれます。

```
BOOL m_bSystemCursor;
```

### <a name="remarks"></a>解説

それ以外の場合は、モジュールに含まれるカーソル リソースが読み込まれます。

`CWndClassInfo`DECLARE_WND_CLASS `m_bSystemCursor` [(CWindowImpl](../../atl/reference/cwindowimpl-class.md)の既定値) または[DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex)マクロが指定されている場合にのみ使用されます。 [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) この場合、TRUE`m_bSystemCursor`に初期化されます。 詳細については[、CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)の概要を参照してください。

## <a name="cwndclassinfom_lpszcursorid"></a><a name="m_lpszcursorid"></a>m_lpszCursorID

カーソル リソースの名前または下位ワードのリソース識別子、上位ワードのゼロを指定します。

```
LPCTSTR m_lpszCursorID;
```

### <a name="remarks"></a>解説

ウィンドウ クラスが登録されると、 で識別されるカーソルへのハンドル`m_lpszCursorID`が取得され[、m_wc](#m_wc)によって格納されます。

`CWndClassInfo`DECLARE_WND_CLASS `m_lpszCursorID` [(CWindowImpl](../../atl/reference/cwindowimpl-class.md)の既定値) または[DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex)マクロが指定されている場合にのみ使用されます。 [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) この場合、IDC_ARROW`m_lpszCursorID`に初期化される。 詳細については[、CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)の概要を参照してください。

## <a name="cwndclassinfom_lpszorigname"></a><a name="m_lpszorigname"></a>m_lpszOrigName

既存のウィンドウ クラスの名前を格納します。

```
LPCTSTR m_lpszOrigName;
```

### <a name="remarks"></a>解説

`CWndClassInfo`は`m_lpszOrigName`、クラス定義に[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)マクロを含める場合にのみ使用されます。 この場合、`CWndClassInfo`で指定されたクラスに基づいてウィンドウ クラスを登録`m_lpszOrigName`します。 詳細については[、CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)の概要を参照してください。

## <a name="cwndclassinfom_szautoname"></a><a name="m_szautoname"></a>次のクラス情報::m_szAutoName

ウィンドウ クラスの名前を保持します。

```
TCHAR m_szAutoName[13];
```

### <a name="remarks"></a>解説

`CWndClassInfo`は`m_szAutoName` `WndClassName` [DECLARE_WND_CLASS_EX、](window-class-macros.md#declare_wnd_class_ex) DECLARE_WND_CLASS に NULL[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)が渡された場合にのみ使用[DECLARE_WND_SUPERCLASS。](window-class-macros.md#declare_wnd_superclass) ATL は、ウィンドウ クラスが登録されるときに名前を作成します。

## <a name="cwndclassinfom_wc"></a><a name="m_wc"></a>m_wc

ウィンドウ クラス情報を[WNDCLASSEX](/windows/win32/api/winuser/ns-winuser-wndclassexw)構造体で維持します。

```
WNDCLASSEX m_wc;
```

### <a name="remarks"></a>解説

[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) [(CWindowImpl](../../atl/reference/cwindowimpl-class.md)の既定値) または[DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex)マクロを指定した場合`m_wc`は、新しいウィンドウ クラスに関する情報が含まれます。

[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)マクロを指定した場合は、`m_wc`スーパークラスに関する情報が含まれます。 [m_lpszOrigName](#m_lpszorigname)と[pWndProc](#pwndproc)は、既存のウィンドウ クラスの名前とウィンドウ プロシージャをそれぞれ保存します。

## <a name="cwndclassinfopwndproc"></a><a name="pwndproc"></a>を:p

既存のウィンドウ クラスのウィンドウ プロシージャへのアクセスポイント。

```
WNDPROC pWndProc;
```

### <a name="remarks"></a>解説

`CWndClassInfo`は`pWndProc`、クラス定義に[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)マクロを含める場合にのみ使用されます。 この場合、`CWndClassInfo`既存のクラスに基づくが、別のウィンドウ プロシージャを使用するウィンドウ クラスを登録します。 既存のウィンドウ クラスのウィンドウ プロシージャは`pWndProc`に保存されます。 詳細については[、CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)の概要を参照してください。

## <a name="cwndclassinforegister"></a><a name="register"></a>登録

[CWindowImpl によって呼び出されます::作成](../../atl/reference/cwindowimpl-class.md#create)ウィンドウ クラスがまだ登録されていない場合に登録します。

```
ATOM Register(WNDPROC* pProc);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[アウト]既存のウィンドウ クラスの元のウィンドウ プロシージャを指定します。

### <a name="return-value"></a>戻り値

成功した場合は、登録されているウィンドウ クラスを一意に識別するアトム。 それ以外の場合は、0 に設定されます。

### <a name="remarks"></a>解説

[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) [(CWindowImpl](../../atl/reference/cwindowimpl-class.md)の既定値) または[DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex)マクロを指定した場合`Register`は、新しいウィンドウ クラスを登録します。 この場合 *、pProc*パラメーターは使用されません。

[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)マクロを指定した場合は、`Register`既存のクラスに基づいているが、別のウィンドウ プロシージャを使用するウィンドウ クラスであるスーパークラスを登録します。 既存のウィンドウ クラスのウィンドウ プロシージャが*pProc*に返されます。

## <a name="see-also"></a>関連項目

[CCom コントロール クラス](../../atl/reference/ccomcontrol-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
