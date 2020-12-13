---
description: '詳細情報: CMultiDocTemplate クラス'
title: CMultiDocTemplate クラス
ms.date: 11/04/2016
f1_keywords:
- CMultiDocTemplate
- AFXWIN/CMultiDocTemplate
- AFXWIN/CMultiDocTemplate::CMultiDocTemplate
helpviewer_keywords:
- CMultiDocTemplate [MFC], CMultiDocTemplate
ms.assetid: 5b8aa328-e461-41d0-b388-00594535e119
ms.openlocfilehash: 70b77c04fed41da3b5f025f6a600b9ecfd4bc89b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331571"
---
# <a name="cmultidoctemplate-class"></a>CMultiDocTemplate クラス

MDI (マルチ ドキュメント インターフェイス) を実装するドキュメント テンプレートを定義します。

## <a name="syntax"></a>構文

```
class CMultiDocTemplate : public CDocTemplate
```

## <a name="members"></a>メンバー

このクラスのメンバー関数は virtual です。 ドキュメントについては、「 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) と [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) 」を参照してください。

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMultiDocTemplate::CMultiDocTemplate](#cmultidoctemplate)|`CMultiDocTemplate` オブジェクトを構築します。|

## <a name="remarks"></a>解説

MDI アプリケーションでは、メインフレームウィンドウをワークスペースとして使用します。このワークスペースでは、ユーザーは0個以上のドキュメントフレームウィンドウを開くことができ、それぞれにドキュメントが表示されます。 MDI の詳細な説明については、「 *ソフトウェア設計のための Windows インターフェイスガイドライン*」を参照してください。

ドキュメントテンプレートでは、次の3種類のクラス間のリレーションシップを定義します。

- [CDocument](../../mfc/reference/cdocument-class.md)から派生するドキュメントクラス。

- ビュークラス。上に一覧表示されているドキュメントクラスのデータを表示します。 このクラスは、 [CView](../../mfc/reference/cview-class.md)、、 `CScrollView` 、またはから派生させることができ `CFormView` `CEditView` ます。 (を直接使用することもでき `CEditView` ます)。

- ビューを含むフレームウィンドウクラス。 MDI ドキュメントテンプレートの場合は、からこのクラスを派生できます `CMDIChildWnd` 。また、ドキュメントフレームウィンドウの動作をカスタマイズする必要がない場合は、独自のクラスを派生させずに [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) を直接使用することもできます。

MDI アプリケーションでは、複数の種類のドキュメントをサポートでき、さまざまな種類のドキュメントを同時に開くことができます。 アプリケーションには、サポートするドキュメントの種類ごとに1つのドキュメントテンプレートがあります。 たとえば、MDI アプリケーションでスプレッドシートとテキストドキュメントの両方がサポートされている場合、アプリケーションには2つのオブジェクトがあり `CMultiDocTemplate` ます。

アプリケーションでは、ユーザーが新しいドキュメントを作成するときにドキュメントテンプレートを使用します。 アプリケーションが複数の種類のドキュメントをサポートしている場合、フレームワークはドキュメントテンプレートからサポートされているドキュメントの種類の名前を取得し、[ファイル] [新規] ダイアログボックスの一覧に表示します。 ユーザーがドキュメントの種類を選択すると、アプリケーションはドキュメントクラスオブジェクト、フレームウィンドウオブジェクト、およびビューオブジェクトを作成し、相互にアタッチします。

コンストラクターを除き、のメンバー関数を呼び出す必要はありません `CMultiDocTemplate` 。 フレームワークは、 `CMultiDocTemplate` オブジェクトを内部で処理します。

の詳細につい `CMultiDocTemplate` ては、「 [ドキュメントテンプレート」と「ドキュメント/ビューの作成プロセス](../../mfc/document-templates-and-the-document-view-creation-process.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)

`CMultiDocTemplate`

## <a name="requirements"></a>要件

**ヘッダー:** afxwin.h

## <a name="cmultidoctemplatecmultidoctemplate"></a><a name="cmultidoctemplate"></a> CMultiDocTemplate::CMultiDocTemplate

`CMultiDocTemplate` オブジェクトを構築します。

```
CMultiDocTemplate(
    UINT nIDResource,
    CRuntimeClass* pDocClass,
    CRuntimeClass* pFrameClass,
    CRuntimeClass* pViewClass);
```

### <a name="parameters"></a>パラメーター

*nIDResource*<br/>
ドキュメントの種類で使用されるリソースの ID を指定します。 これには、メニュー、アイコン、アクセラレータテーブル、および文字列リソースが含まれます。

文字列リソースは、' \n ' 文字で区切られた最大7つの部分文字列で構成されます (サブ文字列が含まれていない場合、' \n ' 文字はプレースホルダーとして必要です)。ただし、末尾の ' \n ' 文字は必要ありません。これらの部分文字列は、ドキュメントの種類を記述します。 部分文字列の詳細については、「 [CDocTemplate:: GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring)」を参照してください。 この文字列リソースは、アプリケーションのリソースファイルにあります。 次に例を示します。

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"
END
```

最初の部分文字列は MDI アプリケーションでは使用されないため、文字列は ' \n ' 文字で始まります。 この文字列は、文字列エディターを使用して編集できます。文字列全体は、7つの個別のエントリとしてではなく、文字列エディターに単一のエントリとして表示されます。

これらのリソースの種類の詳細については、「 [リソースエディター](../../windows/resource-editors.md)」を参照してください。

*pDocClass*<br/>
`CRuntimeClass`ドキュメントクラスのオブジェクトを指します。 このクラスは、 `CDocument` ドキュメントを表すために定義するの派生クラスです。

*pFrameClass*<br/>
`CRuntimeClass`フレームウィンドウクラスのオブジェクトを指します。 このクラスは、派生クラスにすることができ `CMDIChildWnd` `CMDIChildWnd` ます。また、ドキュメントフレームウィンドウに既定の動作が必要な場合は、それ自体にすることもできます。

*pViewClass*<br/>
`CRuntimeClass`ビュークラスのオブジェクトを指します。 このクラスは、 `CView` ドキュメントを表示するために定義するの派生クラスです。

### <a name="remarks"></a>解説

`CMultiDocTemplate`アプリケーションでサポートされているドキュメントの種類ごとに1つのオブジェクトを動的に割り当て、 `CWinApp::AddDocTemplate` `InitInstance` アプリケーションクラスのメンバー関数からそれぞれを渡します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#92](../../mfc/codesnippet/cpp/cmultidoctemplate-class_1.cpp)]

2番目の例を次に示します。

[!code-cpp[NVC_MFCDocView#93](../../mfc/codesnippet/cpp/cmultidoctemplate-class_2.cpp)]

## <a name="see-also"></a>関連項目

[CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)<br/>
[CSingleDocTemplate クラス](../../mfc/reference/csingledoctemplate-class.md)<br/>
[CWinApp クラス](../../mfc/reference/cwinapp-class.md)
