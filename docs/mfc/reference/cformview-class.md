---
description: '詳細情報: CFormView クラス'
title: CFormView クラス
ms.date: 11/04/2016
f1_keywords:
- CFormView
- AFXEXT/CFormView
- AFXEXT/CFormView::CFormView
- AFXEXT/CFormView::IsInitDlgCompleted
helpviewer_keywords:
- CFormView [MFC], CFormView
- CFormView [MFC], IsInitDlgCompleted
ms.assetid: a99ec313-36f0-4f28-9d2b-de11de14ac19
ms.openlocfilehash: ec37a3819f299830fef96bfdf93c0170b2969c66
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184310"
---
# <a name="cformview-class"></a>CFormView クラス

フォーム ビューの基底クラスです。

## <a name="syntax"></a>構文

```
class CFormView : public CScrollView
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[CFormView::CFormView](#cformview)|`CFormView` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CFormView::IsInitDlgCompleted](#isinitdlgcompleted)|初期化中に同期に使用されます。|

## <a name="remarks"></a>解説

フォーム ビューは、基本的には、コントロールを含むビューです。 これらのコントロールは、ダイアログ テンプレート リソースに基づいて配置されます。 アプリケーションでフォームが必要な場合は、`CFormView` を使用します。 これらのビューでは、必要に応じて [CScrollView](../../mfc/reference/cscrollview-class.md) 機能を使用したスクロールがサポートされます。

[Forms-Based アプリケーションを作成](../../mfc/reference/creating-a-forms-based-mfc-application.md)するときは、そのビュークラスをに基づいてフォームベースのアプリケーションにすることができ `CFormView` ます。

ドキュメントビューベースのアプリケーションに新しい [フォームトピック](../../mfc/form-views-mfc.md) を挿入することもできます。 アプリケーションで最初はフォームをサポートしていなかった場合でも、新しいフォームを挿入するときに、Visual C++ によってフォームのサポートが追加されます。

MFC アプリケーション ウィザードと [クラスの追加] コマンドは、フォーム ベースのアプリケーションを作成する方法として推奨されています。 これらの方法を使用せずにフォームベースのアプリケーションを作成する必要がある場合は、「 [Forms-Based アプリケーションの作成](../../mfc/reference/creating-a-forms-based-mfc-application.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

`CFormView`

## <a name="requirements"></a>要件

**ヘッダー:** afxext.h

## <a name="cformviewcformview"></a><a name="cformview"></a> CFormView:: CFormView

`CFormView` オブジェクトを構築します。

```
CFormView(LPCTSTR lpszTemplateName);
CFormView(UINT nIDTemplate);
```

### <a name="parameters"></a>パラメーター

*lpszTemplateName*<br/>
ダイアログテンプレートリソースの名前である null で終わる文字列を格納します。

*nIDTemplate*<br/>
ダイアログテンプレートリソースの ID 番号を格納します。

### <a name="remarks"></a>解説

から派生した型のオブジェクトを作成する場合 `CFormView` は、いずれかのコンストラクターを呼び出してビューオブジェクトを作成し、ビューの基になるダイアログリソースを識別します。 リソースは、名前で識別できます (コンストラクターの引数として文字列を渡すか、または ID で符号なし整数を渡します)。

フォームビューウィンドウと子コントロールは、が呼び出されるまで作成されません `CWnd::Create` 。 `CWnd::Create` は、ドキュメントテンプレートによって駆動されるドキュメントおよびビュー作成プロセスの一部として、フレームワークによって呼び出されます。

> [!NOTE]
> 派生クラスは、独自のコンストラクターを提供 *する必要があり* ます。 コンストラクターで、 `CFormView::CFormView` 上のクラスの概要に示すように、リソース名または ID を引数として指定して、コンストラクターを呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#90](../../mfc/codesnippet/cpp/cformview-class_1.h)]

[!code-cpp[NVC_MFCDocView#91](../../mfc/codesnippet/cpp/cformview-class_2.cpp)]

## <a name="cformviewisinitdlgcompleted"></a><a name="isinitdlgcompleted"></a> CFormView:: IsInitDlgCompleted

他の操作が実行される前に初期化が完了したことを確認するために MFC によって使用されます。

```
BOOL IsInitDlgCompleted() const;
```

### <a name="return-value"></a>戻り値

このダイアログの初期化関数が完了している場合は true。

## <a name="see-also"></a>関連項目

[MFC のサンプル SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[MFC のサンプル VIEWEX](../../overview/visual-cpp-samples.md)<br/>
[CScrollView クラス](../../mfc/reference/cscrollview-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CDialog クラス](../../mfc/reference/cdialog-class.md)<br/>
[CScrollView クラス](../../mfc/reference/cscrollview-class.md)
