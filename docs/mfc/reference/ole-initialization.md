---
title: OLE の初期化
ms.date: 11/04/2016
f1_keywords:
- afxdisp/AfxOleInit
- afxdisp/AfxEnableControlContainer
helpviewer_keywords:
- OLE initialization
ms.assetid: aa8a54a7-24c3-4344-b2c6-dbcf6084fa31
ms.openlocfilehash: 6860697dd3adbe26197dd9075e84f402029e00a5
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78855692"
---
# <a name="ole-initialization"></a>OLE の初期化

アプリケーションで OLE system サービスを使用するには、OLE システム Dll を初期化し、Dll が正しいバージョンであることを確認する必要があります。 `AfxOleInit` 関数は、OLE システム Dll を初期化します。

### <a name="ole-initialization"></a>OLE の初期化

|||
|-|-|
|[AfxOleInit](#afxoleinit)|OLE ライブラリを初期化します。|
|[AfxEnableControlContainer](#afxenablecontrolcontainer)|OLE コントロールのコンテインメントのサポートを有効にするには、アプリケーションオブジェクトの `InitInstance` 関数でこの関数を呼び出します。|

## <a name="afxenablecontrolcontainer"></a>AfxEnableControlContainer

OLE コントロールのコンテインメントのサポートを有効にするには、アプリケーションオブジェクトの `InitInstance` 関数でこの関数を呼び出します。

### <a name="syntax"></a>構文

```
void AfxEnableControlContainer( );
```

### <a name="remarks"></a>解説

OLE コントロール (現在は ActiveX コントロールと呼ばれます) の詳細については、「 [Activex コントロールのトピック](../mfc-activex-controls.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

##  <a name="afxoleinit"></a>AfxOleInit

アプリケーションの OLE サポートを初期化します。

```
BOOL AFXAPI AfxOleInit();
```

### <a name="return-value"></a>戻り値

成功した場合は 0 以外の値です。初期化に失敗した場合は 0 です。失敗の原因は多くの場合、正しくないバージョンの OLE システム DLL がインストールされていることです。

### <a name="remarks"></a>解説

MFC アプリケーションに対する OLE サポートを初期化するには、この関数を呼び出します。 この関数を呼び出すと、次のアクションが発生します。

- 呼び出し元のアプリケーションの現在のアパートメントで COM ライブラリを初期化します。 詳細については、「 [Oleinitialize](/windows/win32/api/ole2/nf-ole2-oleinitialize)」を参照してください。

- [の imessagefilter.prefiltermessage](/windows/win32/api/objidl/nn-objidl-imessagefilter)インターフェイスを実装して、メッセージフィルターオブジェクトを作成します。 このメッセージフィルターには、 [AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter)の呼び出しを使用してアクセスできます。

> [!NOTE]
>  **AfxOleInit**が MFC DLL から呼び出された場合、呼び出しは失敗します。 この関数は DLL から呼び出された場合、呼び出し元アプリケーションによって OLE システムが既に初期化されていることを想定するため、失敗が生じます。

> [!NOTE]
>  MFC アプリケーションは、シングルスレッド アパートメント (STA) として初期化する必要があります。 `InitInstance` override で[CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex)を呼び出した場合は、COINIT_MULTITHREADED ではなく COINIT_APARTMENTTHREADED を指定します。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="see-also"></a>参照

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
