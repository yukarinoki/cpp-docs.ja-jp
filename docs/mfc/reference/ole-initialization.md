---
title: OLE の初期化
ms.date: 11/04/2016
f1_keywords:
- afxdisp/AfxOleInit
- afxdisp/AfxEnableControlContainer
helpviewer_keywords:
- OLE initialization
ms.assetid: aa8a54a7-24c3-4344-b2c6-dbcf6084fa31
ms.openlocfilehash: 39a6f28bfe38f254f15f441ed6305daa2cb5793e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373034"
---
# <a name="ole-initialization"></a>OLE の初期化

アプリケーションが OLE システム サービスを使用するには、OLE システム DLL を初期化し、DLL が正しいバージョンであることを確認する必要があります。 この`AfxOleInit`関数は、OLE システム DLL を初期化します。

### <a name="ole-initialization"></a>OLE の初期化

|||
|-|-|
|[AfxOleInit](#afxoleinit)|OLE ライブラリを初期化します。|
|[AfxEnableControlContainer](#afxenablecontrolcontainer)|アプリケーション オブジェクトの`InitInstance`関数でこの関数を呼び出して、OLE コントロールのコンテインメントのサポートを有効にします。|

## <a name="afxenablecontrolcontainer"></a><a name="afxenablecontrolcontainer"></a>コントロール コンテナ

アプリケーション オブジェクトの`InitInstance`関数でこの関数を呼び出して、OLE コントロールのコンテインメントのサポートを有効にします。

### <a name="syntax"></a>構文

```
void AfxEnableControlContainer( );
```

### <a name="remarks"></a>解説

OLE コントロール (現在は ActiveX コントロール) の詳細については、「 [ActiveX コントロールのトピック](../mfc-activex-controls.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="afxoleinit"></a><a name="afxoleinit"></a>アfxOleInit

アプリケーションの OLE サポートを初期化します。

```
BOOL AFXAPI AfxOleInit();
```

### <a name="return-value"></a>戻り値

成功した場合は 0 以外の値です。初期化に失敗した場合は 0 です。失敗の原因は多くの場合、正しくないバージョンの OLE システム DLL がインストールされていることです。

### <a name="remarks"></a>解説

MFC アプリケーションに対する OLE サポートを初期化するには、この関数を呼び出します。 この関数を呼び出すと、次のアクションが発生します。

- 呼び出し元のアプリケーションの現在のアパートメントで COM ライブラリを初期化します。 詳細については、「 [OleInitialize](/windows/win32/api/ole2/nf-ole2-oleinitialize)」を参照してください。

- [IMessageFilter](/windows/win32/api/objidl/nn-objidl-imessagefilter)インターフェイスを実装するメッセージ フィルター オブジェクトを作成します。 このメッセージ フィルターには[、AfxOleGet メッセージ フィルター](application-control.md#afxolegetmessagefilter)の呼び出しを使用してアクセスできます。

> [!NOTE]
> **AfxOleInit**が MFC DLL から呼び出された場合、呼び出しは失敗します。 この関数は DLL から呼び出された場合、呼び出し元アプリケーションによって OLE システムが既に初期化されていることを想定するため、失敗が生じます。

> [!NOTE]
> MFC アプリケーションは、シングルスレッド アパートメント (STA) として初期化する必要があります。 オーバーライドで[CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex)を`InitInstance`呼び出す場合は、COINIT_MULTITHREADEDではなくCOINIT_APARTMENTTHREADEDを指定します。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
