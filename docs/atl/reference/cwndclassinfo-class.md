---
title: CWndClassInfo クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CWndClassInfo class
ms.assetid: c36fe7e1-75f1-4cf5-a06f-9f59c43fe6fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 878d6065f3a158ac4404620205ef9c60912d89ca
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365765"
---
# <a name="cwndclassinfo-class"></a>CWndClassInfo クラス
このクラスは、ウィンドウ クラスの情報を登録するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
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
|[m_atom](#m_atom)|登録済みのウィンドウ クラスを一意に識別します。|  
|[m_bSystemCursor](#m_bsystemcursor)|システム カーソルまたはモジュールのリソースに含まれているカーソルをカーソル リソースを参照するかどうかを指定します。|  
|[マクロ](#m_lpszcursorid)|カーソル リソースの名前を指定します。|  
|[マクロ](#m_lpszorigname)|既存のウィンドウ クラスの名前が含まれています。|  
|[m_szAutoName](#m_szautoname)|ウィンドウ クラスの ATL 生成の名前を保持します。|  
|[m_wc](#m_wc)|ウィンドウ クラスの情報を保持する**WNDCLASSEX**構造体。|  
|[は](#pwndproc)|既存のウィンドウ クラスのウィンドウ プロシージャを指します。|  
  
## <a name="remarks"></a>コメント  
 `CWndClassInfo` ウィンドウ クラスの情報を管理します。 通常使用する`CWndClassInfo`3 つのマクロのいずれかで`DECLARE_WND_CLASS`、 `DECLARE_WND_CLASS_EX`、または`DECLARE_WND_SUPERCLASS`次の表で説明されている。  
  
|マクロ|説明|  
|-----------|-----------------|  
|[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)|`CWndClassInfo` 新しいウィンドウ クラスの情報を登録します。|  
|[場合は](window-class-macros.md#declare_wnd_class_ex)|`CWndClassInfo` クラスのパラメーターを含む、新しいウィンドウ クラスの情報を登録します。|  
|[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)|`CWndClassInfo` 既存のクラスに基づきますが、別のウィンドウ プロシージャを使用しているウィンドウ クラスの情報を登録します。 この手法をスーパークラス化と呼びます。|  
  
 既定では、 [CWindowImpl](../../atl/reference/cwindowimpl-class.md)が含まれています、`DECLARE_WND_CLASS`新しいウィンドウ クラスに基づいて、マクロをウィンドウを作成します。 DECLARE_WND_CLASS は、コントロールの既定のスタイルと背景色を提供します。 クラスをスタイルを指定して、自分で背景の色にする場合は、派生`CWindowImpl`を含めると、`DECLARE_WND_CLASS_EX`クラスの定義でマクロです。  
  
 既存のウィンドウ クラスに基づくウィンドウを作成する場合は、派生クラスから`CWindowImpl`を含めると、`DECLARE_WND_SUPERCLASS`クラスの定義でマクロです。 例えば:  
  
 [!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwndclassinfo-class_1.h)]  
  
 ウィンドウ クラスの詳細については、次を参照してください。[ウィンドウ クラス](http://msdn.microsoft.com/library/windows/desktop/ms632596)Windows SDK に含まれています。  
  
 詳細については、ATL で windows を使用して、記事を参照してください。 [ATL ウィンドウ クラス](../../atl/atl-window-classes.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
  
##  <a name="m_atom"></a>  CWndClassInfo::m_atom  
 登録済みのウィンドウ クラスの一意の識別子が含まれています。  
  
```
ATOM m_atom;
```  
  
##  <a name="m_bsystemcursor"></a>  CWndClassInfo::m_bSystemCursor  
 場合**TRUE**、ウィンドウ クラスが登録されているときに、システムのカーソル リソースが読み込まれます。  
  
```
BOOL m_bSystemCursor;
```  
  
### <a name="remarks"></a>コメント  
 それ以外の場合は、モジュールに含まれているカーソル リソースが読み込まれます。  
  
 `CWndClassInfo` 使用して`m_bSystemCursor`される場合にのみ、 [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (既定で[CWindowImpl](../../atl/reference/cwindowimpl-class.md)) または[場合は](window-class-macros.md#declare_wnd_class_ex)マクロを指定します。 この場合、`m_bSystemCursor`に初期化される**TRUE**です。 詳細については、次を参照してください。、 [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)の概要です。  
  
##  <a name="m_lpszcursorid"></a>  CWndClassInfo::m_lpszCursorID  
 下位ワードおよび上位ワードにゼロでカーソル リソースの名前またはリソースの識別子のいずれかを指定します。  
  
```
LPCTSTR m_lpszCursorID;
```  
  
### <a name="remarks"></a>コメント  
 ウィンドウ クラスを登録するときに、によって識別されるカーソルを識別するハンドル`m_lpszCursorID`取得され格納されている[m_wc](#m_wc)です。  
  
 `CWndClassInfo` 使用して`m_lpszCursorID`される場合にのみ、 [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (既定で[CWindowImpl](../../atl/reference/cwindowimpl-class.md)) または[場合は](window-class-macros.md#declare_wnd_class_ex)マクロを指定します。 この場合、`m_lpszCursorID`に初期化される**IDC_ARROW**です。 詳細については、次を参照してください。、 [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)の概要です。  
  
##  <a name="m_lpszorigname"></a>  CWndClassInfo::m_lpszOrigName  
 既存のウィンドウ クラスの名前が含まれています。  
  
```
LPCTSTR m_lpszOrigName;
```  
  
### <a name="remarks"></a>コメント  
 `CWndClassInfo` 使用して`m_lpszOrigName`のみを含めるとき、 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)クラスの定義でマクロです。 この場合、`CWndClassInfo`によってという名前のクラスに基づいて、ウィンドウ クラス レジスタ`m_lpszOrigName`です。 詳細については、次を参照してください。、 [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)の概要です。  
  
##  <a name="m_szautoname"></a>  CWndClassInfo::m_szAutoName  
 ウィンドウ クラスの名前を保持します。  
  
```
TCHAR m_szAutoName[13];
```  
  
### <a name="remarks"></a>コメント  
 `CWndClassInfo` 使用して`m_szAutoName`場合にのみ、 **NULL**渡され、`WndClassName`パラメーターを[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)、[場合は](window-class-macros.md#declare_wnd_class_ex)または[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)です。 ATL は、ウィンドウ クラスが登録されているときに、名前が作成します。  
  
##  <a name="m_wc"></a>  CWndClassInfo::m_wc  
 ウィンドウ クラスの情報を保持して、 [WNDCLASSEX](http://msdn.microsoft.com/library/windows/desktop/ms633577)構造体。  
  
```
WNDCLASSEX m_wc;
```  
  
### <a name="remarks"></a>コメント  
 指定した場合、 [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (既定で[CWindowImpl](../../atl/reference/cwindowimpl-class.md)) または[場合は](window-class-macros.md#declare_wnd_class_ex)マクロ、`m_wc`に関する情報を含む、新しいウィンドウ クラスです。  
  
 指定した場合、 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)マクロ、`m_wc`スーパークラスに関する情報が含まれています: ウィンドウ クラスを既存のクラスに基づきますが、別のウィンドウ プロシージャを使用します。 [スーパークラス](#m_lpszorigname)と[は](#pwndproc)既存のウィンドウ クラスの名前とウィンドウ プロシージャをそれぞれに保存します。  
  
##  <a name="pwndproc"></a>  CWndClassInfo::pWndProc  
 既存のウィンドウ クラスのウィンドウ プロシージャを指します。  
  
```
WNDPROC pWndProc;
```  
  
### <a name="remarks"></a>コメント  
 `CWndClassInfo` 使用して`pWndProc`のみを含めるとき、 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)クラスの定義でマクロです。 この場合、`CWndClassInfo`は既存のクラスに基づいていますが、別のウィンドウ プロシージャを使用しているウィンドウ クラスを登録します。 既存のウィンドウ クラスのウィンドウ プロシージャ`pWndProc`です。 詳細については、次を参照してください。、 [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)の概要です。  
  
##  <a name="register"></a>  CWndClassInfo::Register  
 によって呼び出されます[CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create)をまだ登録されていない場合は、ウィンドウ クラスを登録します。  
  
```
ATOM Register(WNDPROC* pProc);
```  
  
### <a name="parameters"></a>パラメーター  
 `pProc`  
 [out]既存のウィンドウ クラスの元のウィンドウ プロシージャを指定します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、atom 一意に識別する、ウィンドウ クラスが登録されています。 それ以外の場合、0 を返します。  
  
### <a name="remarks"></a>コメント  
 指定した場合、 [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (既定で[CWindowImpl](../../atl/reference/cwindowimpl-class.md)) または[場合は](window-class-macros.md#declare_wnd_class_ex)マクロ、`Register`新しいウィンドウ クラスを登録します。 ここで、`pProc`パラメーターは使用されません。  
  
 指定した場合、 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)マクロ、`Register`スーパークラスの登録: ウィンドウ クラスを既存のクラスに基づきますが、別のウィンドウ プロシージャを使用します。 既存のウィンドウ クラスのウィンドウ プロシージャが返される`pProc`です。  
  
## <a name="see-also"></a>関連項目  
 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)