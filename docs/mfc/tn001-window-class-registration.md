---
description: '詳細情報: テクニカルノート 1: Window クラスの登録'
title: 'テクニカル ノート 1: ウィンドウ クラスの登録'
ms.date: 11/04/2016
f1_keywords:
- vc.registration
helpviewer_keywords:
- TN001
- WNDCLASS [MFC]
- AfxRegisterClass function
ms.assetid: 1abf678e-f220-4606-85e0-03df32f64c54
ms.openlocfilehash: fc54b6f783a50bb35f87f542772b9a1921f1f7b7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216107"
---
# <a name="tn001-window-class-registration"></a>テクニカル ノート 1: ウィンドウ クラスの登録

このメモでは、Microsoft Windows で必要な特殊な [WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw)を登録する MFC ルーチンについて説明します。 `WNDCLASS`MFC と Windows で使用される特定の属性について説明します。

## <a name="the-problem"></a>問題

[CWnd](../mfc/reference/cwnd-class.md)オブジェクトの属性 ( `HWND` Windows のハンドルなど) は、ウィンドウオブジェクトとの2か所に格納されます `WNDCLASS` 。 の名前は、 `WNDCLASS` *lpszclassname* パラメーターの [CWnd:: create](../mfc/reference/cwnd-class.md#create)や [CFrameWnd:: create](../mfc/reference/cframewnd-class.md#create)などの一般的なウィンドウ作成関数に渡されます。

これは `WNDCLASS` 、次の4つのいずれかの方法で登録する必要があります。

- 指定された MFC を使用して暗黙的に `WNDCLASS` 。

- Windows コントロール (またはその他のコントロール) をサブクラス化することによって暗黙的にします。

- MFC の [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) または [AfxRegisterClass](../mfc/reference/application-information-and-management.md#afxregisterclass)を呼び出すことによって明示的に指定します。

- Windows ルーチン [RegisterClass](/windows/win32/api/winuser/nf-winuser-registerclassw)を呼び出して明示的に指定します。

## <a name="wndclass-fields"></a>WNDCLASS のフィールド

`WNDCLASS`構造体は、ウィンドウクラスを記述するさまざまなフィールドで構成されます。 次の表は、これらのフィールドと、それらを MFC アプリケーションで使用する方法を示しています。

|フィールド|説明|
|-----------|-----------------|
|*lpfnWndProc*|ウィンドウプロシージャは、である必要があります。 `AfxWndProc`|
|*cbClsExtra*|使用されていません (ゼロにする必要があります)|
|*cbWndExtra*|使用されていません (ゼロにする必要があります)|
|*hInstance*|[AfxGetInstanceHandle](../mfc/reference/application-information-and-management.md#afxgetinstancehandle)で自動的に入力されます|
|*hIcon*|フレームウィンドウのアイコン、以下を参照|
|*hCursor*|マウスがウィンドウ上にあるときのカーソル。以下を参照|
|*hbrBackground*|背景色、以下を参照|
|*lpszMenuName*|使用されていません (NULL にする必要があります)|
|*lpszClassName*|クラス名、以下を参照|

## <a name="provided-wndclasses"></a>指定された WNDCLASSes

以前のバージョンの MFC (MFC 4.0 より前) では、いくつかの定義済みのウィンドウクラスが用意されています。 これらのウィンドウクラスは、既定では提供されなくなりました。 アプリケーションでは `AfxRegisterWndClass` 、適切なパラメーターを指定してを使用する必要があります。

アプリケーションが指定されたリソース ID (AFX_IDI_STD_FRAME など) のリソースを提供する場合、MFC はそのリソースを使用します。 それ以外の場合は、既定のリソースが使用されます。 アイコンの場合は標準のアプリケーションアイコンが使用され、カーソルの場合は標準の矢印カーソルが使用されます。

2つのアイコンは、1つのドキュメントの種類を持つ MDI アプリケーションをサポートします。メインアプリケーション用の1つのアイコンです。ドキュメント/MDIChild ウィンドウをアイコン化するためのアイコンです。 アイコンが異なる複数のドキュメントの種類については、追加の es を登録する `WNDCLASS` か、 [CFrameWnd:: LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) 関数を使用する必要があります。

`CFrameWnd::LoadFrame` は、 `WNDCLASS` 最初のパラメーターとして指定したアイコン ID と、次の標準属性を使用してを登録します。

- クラススタイル: CS_DBLCLKS &#124; CS_HREDRAW &#124; CS_VREDRAW;

- アイコン AFX_IDI_STD_FRAME

- 矢印カーソル

- COLOR_WINDOW 背景色

のクライアント領域 [](../mfc/reference/cmdiframewnd-class.md) `CMDIFrameWnd` は **MDICLIENT** ウィンドウで完全にカバーされているため、CMDIFrameWnd の背景色とカーソルの値は使用されません。 Microsoft では、可能な限り標準の色とカーソルの種類を使用するように、 **MDICLIENT** ウィンドウのサブクラス化を推奨していません。

## <a name="subclassing-and-superclassing-controls"></a>サブクラス化と Superclassing コントロール

Windows コントロール (たとえば、 [CButton](../mfc/reference/cbutton-class.md)) をサブクラス化またはスーパークラス化すると、 `WNDCLASS` そのコントロールの windows 実装で提供されている属性がクラスによって自動的に取得されます。

## <a name="the-afxregisterwndclass-function"></a>AfxRegisterWndClass 関数

MFC には、ウィンドウクラスを登録するためのヘルパー関数が用意されています。 一連の属性 (ウィンドウクラスのスタイル、カーソル、背景ブラシ、アイコン) を指定すると、合成名が生成され、結果のウィンドウクラスが登録されます。 たとえば、次のように入力します。

```
const char* AfxRegisterWndClass(UINT nClassStyle,
    HCURSOR hCursor,
    HBRUSH hbrBackground,
    HICON hIcon);
```

この関数は、生成された登録済みウィンドウクラス名の一時文字列を返します。 この関数の詳細については、「 [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass)」を参照してください。

返される文字列は、静的な文字列バッファーへの一時ポインターです。 これは、次にが呼び出されるまで有効です `AfxRegisterWndClass` 。 この文字列をそのままにしたい場合は、次の例のように、 [CString](../atl-mfc-shared/using-cstring.md) 変数に格納します。

```
CString strWndClass = AfxRegisterWndClass(CS_DBLCLK, ...);

...
CWnd* pWnd = new CWnd;
pWnd->Create(strWndClass, ...);

...
```

`AfxRegisterWndClass` ウィンドウクラスの登録に失敗した場合 (パラメーターが正しくないか、Windows のメモリが不足しているため)、は [Cresourceexception](../mfc/reference/cresourceexception-class.md) をスローします。

## <a name="the-registerclass-and-afxregisterclass-functions"></a>RegisterClass 関数と AfxRegisterClass 関数

より高度な操作を行う場合は、 `AfxRegisterWndClass` WINDOWS API `RegisterClass` または MFC 関数を呼び出すことができ `AfxRegisterClass` ます。 `CWnd`、 [CFrameWnd](../mfc/reference/cframewnd-class.md) 、および [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)関数は、 `Create` 最初のパラメーターとして window クラスの *lpszclassname* 文字列名を受け取ります。 登録時に使用したメソッドに関係なく、任意の登録済みウィンドウクラス名を使用できます。

`AfxRegisterClass`Win32 の DLL で (または) を使用することが重要です `AfxRegisterWndClass` 。 Win32 では、DLL によって登録されたクラスの登録が自動的に解除されないため、DLL を終了するときに明示的にクラスの登録を解除する必要があります。 で `AfxRegisterClass` はなくを使用 `RegisterClass` すると、自動的に処理されます。 `AfxRegisterClass` は、DLL によって登録された一意のクラスのリストを保持し、DLL が終了したときに自動的に登録を解除します。 DLL でを使用する場合は、 `RegisterClass` ( [DllMain](/windows/win32/Dlls/dllmain) 関数で) dll が終了したときに、すべてのクラスが登録解除されるようにする必要があります。 そうしない `RegisterClass` と、別のクライアントアプリケーションが DLL を使用しようとしたときに、が予期せず失敗する可能性があります。

## <a name="see-also"></a>関連項目

[番号別テクニカルノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカルノート](../mfc/technical-notes-by-category.md)
