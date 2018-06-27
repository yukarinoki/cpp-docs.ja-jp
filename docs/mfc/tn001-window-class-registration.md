---
title: 'TN001: ウィンドウ クラスの登録 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.registration
dev_langs:
- C++
helpviewer_keywords:
- TN001
- WNDCLASS [MFC]
- AfxRegisterClass function
ms.assetid: 1abf678e-f220-4606-85e0-03df32f64c54
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e0be2e87f77e047e1b29d99e562a67bb9f4f1ee9
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951979"
---
# <a name="tn001-window-class-registration"></a>テクニカル ノート 1: ウィンドウ クラスの登録
このメモには、特別なを登録する MFC ルーチンがについて説明[WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576)es Microsoft Windows で必要とします。 特定`WNDCLASS`MFC と Windows で使用される属性がについて説明します。  
  
## <a name="the-problem"></a>問題を  
 属性、 [CWnd](../mfc/reference/cwnd-class.md)オブジェクトと同様に、 `HWND` Windows での処理、2 つの場所に格納されます: ウィンドウ オブジェクトおよび`WNDCLASS`です。 名前、`WNDCLASS`など、全般的なウィンドウ作成関数に渡される[cwnd::create](../mfc/reference/cwnd-class.md#create)と[CFrameWnd::Create](../mfc/reference/cframewnd-class.md#create)で、 *lpszClassName*パラメーター。  
  
 これは、 `WNDCLASS` 4 つの手段の 1 つによって登録される必要があります。  
  
-   指定された MFC を使用して暗黙的に`WNDCLASS`です。  
  
-   Windows コントロール (または他のコントロール) をサブクラス化を暗黙的にします。  
  
-   MFC を呼び出すことによって明示的に[AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass)または[AfxRegisterClass](../mfc/reference/application-information-and-management.md#afxregisterclass)です。  
  
-   Windows ルーチンを呼び出すことによって明示的に[RegisterClass](http://msdn.microsoft.com/library/windows/desktop/ms633586)です。  
  
## <a name="wndclass-fields"></a>WNDCLASS フィールド  
 `WNDCLASS`ウィンドウ クラスを記述するさまざまなフィールドの構造で構成されます。 次の表は、フィールドに表示し、MFC アプリケーションでの使用方法を指定します。  
  
|フィールド|説明|  
|-----------|-----------------|  
|*lpfnWndProc*|ウィンドウ プロシージャがある必要があります、 `AfxWndProc`|  
|*cbClsExtra*|使用されません (0 にする必要があります)|  
|*cbWndExtra*|使用されません (0 にする必要があります)|  
|*hInstance*|自動的に入力[AfxGetInstanceHandle](../mfc/reference/application-information-and-management.md#afxgetinstancehandle)|  
|*hIcon*|フレーム ウィンドウのアイコンは、以下を参照してください。|  
|*hCursor*|下のウィンドウで、上にマウスをカーソルを参照してください。|  
|*hbrBackground*|背景色、以下を参照してください。|  
|*lpszMenuName*|使用されません (NULL にする必要があります)|  
|*lpszClassName*|クラス名、以下を参照してください。|  
  
## <a name="provided-wndclasses"></a>WNDCLASSes の提供  
 以前のバージョンの MFC (MFC 4.0 の場合) の前にいくつかの定義済みウィンドウ クラスを提供します。 これらのウィンドウ クラスは既定では提供されません。 アプリケーションを使用する必要があります`AfxRegisterWndClass`適切なパラメーターを使用します。  
  
 アプリケーションでは、指定されたリソース ID (たとえば、AFX_IDI_STD_FRAME) のリソースを提供する場合、MFC はそのリソースを使用します。 それ以外の場合、既定のリソースが使用されます。 アイコン、アイコンの標準的なアプリケーションを使用すると、され、カーソル、標準の矢印カーソルを使用します。  
  
 2 つのアイコンが 1 つのドキュメントの種類の MDI アプリケーションをサポートします。 メイン アプリケーションの 1 つのアイコン、あります windows の他のアイコン。 アイコンが異なる複数のドキュメントの種類を追加する必要があります登録`WNDCLASS`es またはを使用して、 [CFrameWnd::LoadFrame](../mfc/reference/cframewnd-class.md#loadframe)関数。  
  
 `CFrameWnd::LoadFrame` 登録は、`WNDCLASS`最初のパラメーターと、次の標準的な属性として指定したアイコン ID を使用します。  
  
-   クラスのスタイル: CS_DBLCLKS &#124; CS_HREDRAW &#124; CS_VREDRAW です。  
  
-   AFX_IDI_STD_FRAME アイコン  
  
-   矢印カーソル  
  
-   COLOR_WINDOW 背景色  
  
 背景色とのカーソルの値、 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)ためのクライアント領域は使用されません、`CMDIFrameWnd`に完全に覆わ、 **MDICLIENT**ウィンドウです。 Microsoft のサブクラス化を促す効果はありません、 **MDICLIENT**ウィンドウは、ので、標準の色と可能な場合は、カーソルの種類に使用します。  
  
## <a name="subclassing-and-superclassing-controls"></a>サブクラスとスーパークラス化コントロール  
 サブクラスまたはスーパークラス Windows 制御する場合 (たとえば、 [CButton](../mfc/reference/cbutton-class.md)) クラスを自動的に取得し、`WNDCLASS`そのコントロールの Windows 実装で提供される属性です。  
  
## <a name="the-afxregisterwndclass-function"></a>AfxRegisterWndClass 関数  
 MFC には、ウィンドウ クラスを登録するためのヘルパー関数が用意されています。 一連の属性 (ウィンドウ クラス スタイル、カーソル、背景のブラシ、およびアイコン) を指定するには、合成名が生成され、結果のウィンドウ クラスが登録されています。 たとえば、オブジェクトに適用された  
  
```  
const char* AfxRegisterWndClass(UINT nClassStyle,
    HCURSOR hCursor,
    HBRUSH hbrBackground,
    HICON hIcon);
```  
  
 この関数は、生成された登録済みのウィンドウ クラス名の一時的な文字列を返します。 この関数の詳細については、次を参照してください。 [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass)です。  
  
 返される文字列は、静的な文字列バッファーに一時的なポインターです。 これが有効では、次の呼び出しまで`AfxRegisterWndClass`です。 この文字列を保持する場合は、保存、 [CString](../atl-mfc-shared/using-cstring.md)例のように、変数。  
  
```  
CString strWndClass = AfxRegisterWndClass(CS_DBLCLK, ...);

...  
CWnd* pWnd = new CWnd;  
pWnd->Create(strWndClass, ...);

...  
```  
  
 `AfxRegisterWndClass` スローされます、[関数](../mfc/reference/cresourceexception-class.md)(により無効なパラメーターは、または Windows のメモリ不足) を登録する、ウィンドウ クラスが失敗したかどうか。  
  
## <a name="the-registerclass-and-afxregisterclass-functions"></a>RegisterClass および AfxRegisterClass 関数  
 実行する場合は、何もより高度なより`AfxRegisterWndClass`を提供する Windows API を呼び出すことができます`RegisterClass`または MFC 関数`AfxRegisterClass`です。 `CWnd`、 [CFrameWnd](../mfc/reference/cframewnd-class.md)と[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) `Create`関数、 *lpszClassName*ウィンドウ クラスを最初のパラメーターとしての文字列名。 登録時に使用する方法に関係なく、すべての登録済みのウィンドウ クラス名を使用することができます。  
  
 使用することが重要`AfxRegisterClass`(または`AfxRegisterWndClass`) で Win32 DLL にします。 Win32 は自動的に登録解除されないため、DLL が終了した場合に、明示的に登録を解除する必要があります、DLL によって登録されたクラスです。 使用して`AfxRegisterClass`の代わりに`RegisterClass`これは自動的に処理するためです。 `AfxRegisterClass` 一意のクラスの一覧は、DLL に登録されているしは自動的に解除して、DLL が終了するときは保持します。 使用すると`RegisterClass`DLL で DLL が終了した場合には、すべてのクラスが登録されているないことを確認する必要があります (で、 [DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583)関数)。 そのためにはエラーが発生する可能性があります`RegisterClass`別のクライアント アプリケーションが DLL を使用しようとしたときに予期せず失敗します。  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

