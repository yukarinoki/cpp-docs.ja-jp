---
title: CMultiDocTemplate クラス
ms.date: 11/04/2016
f1_keywords:
- CMultiDocTemplate
- AFXWIN/CMultiDocTemplate
- AFXWIN/CMultiDocTemplate::CMultiDocTemplate
helpviewer_keywords:
- CMultiDocTemplate [MFC], CMultiDocTemplate
ms.assetid: 5b8aa328-e461-41d0-b388-00594535e119
ms.openlocfilehash: 3b3f239b05b1cf7661929333e2d616acce6bedb0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319742"
---
# <a name="cmultidoctemplate-class"></a>CMultiDocTemplate クラス

MDI (マルチ ドキュメント インターフェイス) を実装するドキュメント テンプレートを定義します。

## <a name="syntax"></a>構文

```
class CMultiDocTemplate : public CDocTemplate
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[テンプレート::C マルチドックテンプレート](#cmultidoctemplate)|`CMultiDocTemplate` オブジェクトを構築します。|

## <a name="remarks"></a>解説

MDI アプリケーションでは、メイン フレーム ウィンドウをワークスペースとして使用し、ユーザーは 0 個以上のドキュメント フレーム ウィンドウを開くことができます。 MDI の詳細については、「*ソフトウェア設計に関する Windows インターフェイスガイドライン*」を参照してください。

ドキュメント テンプレートは、次の 3 種類のクラス間の関係を定義します。

- ドキュメント クラスを[CDocument](../../mfc/reference/cdocument-class.md)から派生します。

- 上記のドキュメント クラスのデータを表示するビュー クラス。 このクラスは、 [CView](../../mfc/reference/cview-class.md)、 `CScrollView` `CFormView`、 `CEditView`、 、または から派生させることができます。 (直接使用`CEditView`することもできます。

- ビューを含むフレーム ウィンドウ クラス。 MDI ドキュメント テンプレートの場合は、このクラスを`CMDIChildWnd`から派生させることができます。 [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)

MDI アプリケーションは、複数の種類のドキュメントをサポートでき、異なる種類のドキュメントを同時に開くことができます。 アプリケーションでは、サポートするドキュメントの種類ごとに 1 つのドキュメント テンプレートがあります。 たとえば、MDI アプリケーションがスプレッドシートとテキスト ドキュメントの両方をサポートしている場合、アプリケーション`CMultiDocTemplate`には 2 つのオブジェクトがあります。

ユーザーが新しいドキュメントを作成するときに、アプリケーションはドキュメント テンプレートを使用します。 アプリケーションが複数の種類のドキュメントをサポートしている場合、フレームワークはドキュメント テンプレートからサポートされているドキュメント タイプの名前を取得し、[新規作成] ダイアログ ボックスの一覧に表示します。 ユーザーがドキュメントタイプを選択すると、アプリケーションはドキュメントクラスオブジェクト、フレームウィンドウオブジェクト、およびビューオブジェクトを作成し、互いに関連付けます。

コンストラクター以外の`CMultiDocTemplate`メンバー関数を呼び出す必要はありません。 フレームワークはオブジェクト`CMultiDocTemplate`を内部的に処理します。

の詳細については、「[ドキュメント テンプレートとドキュメント/ビュー作成プロセス](../../mfc/document-templates-and-the-document-view-creation-process.md)」を参照してください。 `CMultiDocTemplate`

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)

`CMultiDocTemplate`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cmultidoctemplatecmultidoctemplate"></a><a name="cmultidoctemplate"></a>テンプレート::C マルチドックテンプレート

`CMultiDocTemplate` オブジェクトを構築します。

```
CMultiDocTemplate(
    UINT nIDResource,
    CRuntimeClass* pDocClass,
    CRuntimeClass* pFrameClass,
    CRuntimeClass* pViewClass);
```

### <a name="parameters"></a>パラメーター

*リソース*<br/>
ドキュメントタイプで使用されるリソースの ID を指定します。 これには、メニュー、アイコン、アクセラレータ テーブル、および文字列リソースが含まれます。

文字列リソースは、'\n' 文字で区切られた最大 7 個の部分文字列で構成されます (部分文字列が含まれていない場合は、"\n" 文字がプレースホルダとして必要になりますが、末尾の '\n' 文字は必要ありません)。これらの部分文字列はドキュメントタイプを記述します。 サブストリングの詳細については[、「CDoc テンプレート::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring)」を参照してください。 この文字列リソースは、アプリケーションのリソース ファイルにあります。 次に例を示します。

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"
END
```

文字列は '\n' 文字で始まることに注意してください。これは、最初の部分文字列が MDI アプリケーションで使用されないため、含まれていないためです。 この文字列は、文字列エディタを使用して編集できます。文字列全体が、7 つの個別のエントリではなく、文字列エディタ内の単一のエントリとして表示されます。

これらのリソースの種類の詳細については、「[リソース エディタ](../../windows/resource-editors.md)」を参照してください。

*クラス*<br/>
ドキュメント クラス`CRuntimeClass`のオブジェクトへのポイント。 このクラスは、`CDocument`ドキュメントを表すために定義する派生クラスです。

*クラス*<br/>
フレーム ウィンドウ`CRuntimeClass`クラスのオブジェクトへのポイント。 このクラスは`CMDIChildWnd`、-derived クラスにすることも、ドキュメント`CMDIChildWnd`フレーム ウィンドウの既定の動作を行う場合は、それ自体にすることもできます。

*クラスを表示します。*<br/>
ビュー クラス`CRuntimeClass`のオブジェクトへのポイント。 このクラスは、`CView`ドキュメントを表示するために定義する派生クラスです。

### <a name="remarks"></a>解説

アプリケーションがサポートする`CMultiDocTemplate`ドキュメントの種類ごとに 1 つのオブジェクトを動的に割り`CWinApp::AddDocTemplate`当て`InitInstance`、アプリケーション クラスのメンバー関数から各オブジェクトを渡します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#92](../../mfc/codesnippet/cpp/cmultidoctemplate-class_1.cpp)]

2 番目の例を次に示します。

[!code-cpp[NVC_MFCDocView#93](../../mfc/codesnippet/cpp/cmultidoctemplate-class_2.cpp)]

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/cdoctemplate-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/cdoctemplate-class.md)<br/>
[CSingleDocTemplate クラス](../../mfc/reference/csingledoctemplate-class.md)<br/>
[CWinApp クラス](../../mfc/reference/cwinapp-class.md)
