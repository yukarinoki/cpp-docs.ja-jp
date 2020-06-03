---
title: CSingleDocTemplate クラス
ms.date: 11/04/2016
f1_keywords:
- CSingleDocTemplate
- AFXWIN/CSingleDocTemplate
- AFXWIN/CSingleDocTemplate::CSingleDocTemplate
helpviewer_keywords:
- CSingleDocTemplate [MFC], CSingleDocTemplate
ms.assetid: 4f3a8212-81ee-48a0-ad22-e0ed7c36a391
ms.openlocfilehash: 5a014b35a6cd2d12367e190e4d6dd689e28eae66
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318348"
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
|[テンプレートを使用します。](#csingledoctemplate)|`CSingleDocTemplate` オブジェクトを構築します。|

## <a name="remarks"></a>解説

SDI アプリケーションでは、メイン フレーム ウィンドウを使用してドキュメントを表示します。一度に開くことができるドキュメントは 1 つだけです。

ドキュメント テンプレートは、次の 3 種類のクラスの間の関係を定義します。

- から派生するドキュメント クラス`CDocument`。

- 上記のドキュメント クラスのデータを表示するビュー クラス。 このクラス`CView`は、 `CScrollView`、 、 `CFormView`、 `CEditView`、 、 から派生できます。 (直接使用`CEditView`することもできます。

- ビューを含むフレーム ウィンドウ クラス。 SDI ドキュメント テンプレートの場合、このクラスをから`CFrameWnd`派生させることができます。メイン フレーム ウィンドウの動作をカスタマイズする必要がない場合は、独自のクラス`CFrameWnd`を派生させずに直接使用できます。

SDI アプリケーションは通常、1 種類のドキュメントをサポートするため、`CSingleDocTemplate`オブジェクトは 1 つだけです。 一度に開くことができるドキュメントは 1 つだけです。

コンストラクター`CSingleDocTemplate`以外のメンバー関数を呼び出す必要はありません。 フレームワークはオブジェクト`CSingleDocTemplate`を内部的に処理します。

の使用`CSingleDocTemplate`の詳細については、「[ドキュメント テンプレートとドキュメント/ビュー作成プロセス](../../mfc/document-templates-and-the-document-view-creation-process.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)

`CSingleDocTemplate`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="csingledoctemplatecsingledoctemplate"></a><a name="csingledoctemplate"></a>テンプレートを使用します。

`CSingleDocTemplate` オブジェクトを構築します。

```
CSingleDocTemplate(
    UINT nIDResource,
    CRuntimeClass* pDocClass,
    CRuntimeClass* pFrameClass,
    CRuntimeClass* pViewClass);
```

### <a name="parameters"></a>パラメーター

*リソース*<br/>
ドキュメントタイプで使用されるリソースの ID を指定します。 これには、メニュー、アイコン、アクセラレータ テーブル、および文字列リソースが含まれます。

文字列リソースは、'\n' 文字で区切られた最大 7 個の部分文字列で構成されます (部分文字列が含まれていない場合はプレースホルダとして '\n' 文字が必要です。これらの部分文字列はドキュメントタイプを記述します。 サブストリングの詳細については[、「CDoc テンプレート::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring)」を参照してください。 この文字列リソースは、アプリケーションのリソース ファイルにあります。 次に例を示します。

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_MAINFRAME "MyCalc Windows Application\nSheet\nWorksheet\n Worksheets (*.myc)\n.myc\nMyCalcSheet\n MyCalc Worksheet"
END
```

この文字列は、文字列エディタを使用して編集できます。文字列全体が、7 つの個別のエントリではなく、文字列エディタ内の単一のエントリとして表示されます。

これらのリソースの種類の詳細については、「[文字列エディタ](../../windows/string-editor.md)」を参照してください。

*クラス*<br/>
ドキュメント クラス`CRuntimeClass`のオブジェクトへのポイント。 このクラスは、`CDocument`ドキュメントを表すために定義する派生クラスです。

*クラス*<br/>
フレーム ウィンドウ`CRuntimeClass`クラスのオブジェクトへのポイント。 このクラスは`CFrameWnd`、派生クラスにすることも、メイン フレーム`CFrameWnd`ウィンドウの既定の動作を行う場合は、それ自体にすることもできます。

*クラスを表示します。*<br/>
ビュー クラス`CRuntimeClass`のオブジェクトへのポイント。 このクラスは、`CView`ドキュメントを表示するために定義する派生クラスです。

### <a name="remarks"></a>解説

オブジェクトを`CSingleDocTemplate`動的に割り当て、`CWinApp::AddDocTemplate`アプリケーション`InitInstance`クラスのメンバー関数から渡します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocViewSDI#13](../../mfc/codesnippet/cpp/csingledoctemplate-class_1.cpp)]

[!code-cpp[NVC_MFCDocViewSDI#14](../../mfc/codesnippet/cpp/csingledoctemplate-class_2.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル ドッキングツール](../../overview/visual-cpp-samples.md)<br/>
[クラス](../../mfc/reference/cdoctemplate-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/cdoctemplate-class.md)<br/>
[CDocument クラス](../../mfc/reference/cdocument-class.md)<br/>
[CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)<br/>
[CMultiDocTemplate クラス](../../mfc/reference/cmultidoctemplate-class.md)<br/>
[Cビュークラス](../../mfc/reference/cview-class.md)<br/>
[CWinApp クラス](../../mfc/reference/cwinapp-class.md)
