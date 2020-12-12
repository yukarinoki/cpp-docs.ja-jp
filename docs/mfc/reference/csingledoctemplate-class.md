---
description: '詳細情報: CSingleDocTemplate クラス'
title: CSingleDocTemplate クラス
ms.date: 11/04/2016
f1_keywords:
- CSingleDocTemplate
- AFXWIN/CSingleDocTemplate
- AFXWIN/CSingleDocTemplate::CSingleDocTemplate
helpviewer_keywords:
- CSingleDocTemplate [MFC], CSingleDocTemplate
ms.assetid: 4f3a8212-81ee-48a0-ad22-e0ed7c36a391
ms.openlocfilehash: 611cada1c90fa776bafb78f0856658cd1bd0a8e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264623"
---
# <a name="csingledoctemplate-class"></a>CSingleDocTemplate クラス

SDI (シングル ドキュメント インターフェイス) を実装するドキュメント テンプレートを定義します。

## <a name="syntax"></a>構文

```
class CSingleDocTemplate : public CDocTemplate
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CSingleDocTemplate::CSingleDocTemplate](#csingledoctemplate)|`CSingleDocTemplate` オブジェクトを構築します。|

## <a name="remarks"></a>解説

SDI アプリケーションは、メインフレームウィンドウを使用してドキュメントを表示します。一度に開くことができるドキュメントは1つだけです。

ドキュメントテンプレートでは、次の3種類のクラス間のリレーションシップを定義します。

- から派生するドキュメントクラス `CDocument` 。

- ビュークラス。上に一覧表示されているドキュメントクラスのデータを表示します。 このクラスは、、、 `CView` 、またはから派生させることができ `CScrollView` `CFormView` `CEditView` ます。 (を直接使用することもでき `CEditView` ます)。

- ビューを含むフレームウィンドウクラス。 SDI ドキュメントテンプレートでは、このクラスをから派生させることができ `CFrameWnd` ます。メインフレームウィンドウの動作をカスタマイズする必要がない場合は、独自のクラスを派生させずにを直接使用することができ `CFrameWnd` ます。

SDI アプリケーションは通常、1種類のドキュメントをサポートしているため、オブジェクトは1つだけ `CSingleDocTemplate` です。 一度に開くことができるドキュメントは1つだけです。

コンストラクターを除き、のメンバー関数を呼び出す必要はありません `CSingleDocTemplate` 。 フレームワークは、 `CSingleDocTemplate` オブジェクトを内部で処理します。

の使用方法の詳細については `CSingleDocTemplate` 、「 [ドキュメントテンプレート」と「ドキュメント/ビューの作成プロセス](../../mfc/document-templates-and-the-document-view-creation-process.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)

`CSingleDocTemplate`

## <a name="requirements"></a>要件

**ヘッダー:** afxwin.h

## <a name="csingledoctemplatecsingledoctemplate"></a><a name="csingledoctemplate"></a> CSingleDocTemplate::CSingleDocTemplate

`CSingleDocTemplate` オブジェクトを構築します。

```
CSingleDocTemplate(
    UINT nIDResource,
    CRuntimeClass* pDocClass,
    CRuntimeClass* pFrameClass,
    CRuntimeClass* pViewClass);
```

### <a name="parameters"></a>パラメーター

*nIDResource*<br/>
ドキュメントの種類で使用されるリソースの ID を指定します。 これには、メニュー、アイコン、アクセラレータテーブル、および文字列リソースが含まれます。

文字列リソースは、' \n ' 文字で区切られた最大7つの部分文字列で構成されます (部分文字列が含まれていない場合、' \n ' 文字はプレースホルダーとして必要です)。ただし、末尾の ' \n ' 文字は必要ありません)。これらの部分文字列は、ドキュメントの種類を記述します。 部分文字列の詳細については、「 [CDocTemplate:: GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring)」を参照してください。 この文字列リソースは、アプリケーションのリソースファイルにあります。 次に例を示します。

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_MAINFRAME "MyCalc Windows Application\nSheet\nWorksheet\n Worksheets (*.myc)\n.myc\nMyCalcSheet\n MyCalc Worksheet"
END
```

この文字列は、文字列エディターを使用して編集できます。文字列全体は、7つの個別のエントリとしてではなく、文字列エディターに単一のエントリとして表示されます。

これらのリソースの種類の詳細については、「 [文字列エディター](../../windows/string-editor.md)」を参照してください。

*pDocClass*<br/>
`CRuntimeClass`ドキュメントクラスのオブジェクトを指します。 このクラスは、 `CDocument` ドキュメントを表すために定義するの派生クラスです。

*pFrameClass*<br/>
`CRuntimeClass`フレームウィンドウクラスのオブジェクトを指します。 このクラスは、派生クラスにすることも `CFrameWnd` 、 `CFrameWnd` メインフレームウィンドウの既定の動作が必要な場合は、それ自体にすることもできます。

*pViewClass*<br/>
`CRuntimeClass`ビュークラスのオブジェクトを指します。 このクラスは、 `CView` ドキュメントを表示するために定義するの派生クラスです。

### <a name="remarks"></a>解説

オブジェクトを動的 `CSingleDocTemplate` に割り当て、 `CWinApp::AddDocTemplate` `InitInstance` アプリケーションクラスのメンバー関数からに渡します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocViewSDI#13](../../mfc/codesnippet/cpp/csingledoctemplate-class_1.cpp)]

[!code-cpp[NVC_MFCDocViewSDI#14](../../mfc/codesnippet/cpp/csingledoctemplate-class_2.cpp)]

## <a name="see-also"></a>関連項目

[MFC のサンプル DOCKTOOL](../../overview/visual-cpp-samples.md)<br/>
[CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)<br/>
[CDocument クラス](../../mfc/reference/cdocument-class.md)<br/>
[CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)<br/>
[CMultiDocTemplate クラス](../../mfc/reference/cmultidoctemplate-class.md)<br/>
[CView クラス](../../mfc/reference/cview-class.md)<br/>
[CWinApp クラス](../../mfc/reference/cwinapp-class.md)
