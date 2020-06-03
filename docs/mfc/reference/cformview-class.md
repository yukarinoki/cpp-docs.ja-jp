---
title: クラスを表示します。
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
ms.openlocfilehash: a9b897c661731878f0bf78c9d04ae7c4ba28cd42
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373802"
---
# <a name="cformview-class"></a>クラスを表示します。

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

フォーム ビューは、基本的には、コントロールを含むビューです。 これらのコントロールは、ダイアログ テンプレート リソースに基づいて配置されます。 アプリケーションでフォームが必要な場合は、`CFormView` を使用します。 これらのビューは、必要に応じて[、CScrollView](../../mfc/reference/cscrollview-class.md)機能を使用してスクロールをサポートします。

[フォーム ベース のアプリケーション を作成](../../mfc/reference/creating-a-forms-based-mfc-application.md)する場合は、フォーム ベースの`CFormView`アプリケーションに設定したビュー クラスを基に設定できます。

また、ドキュメント ビュー ベースのアプリケーションに新しい[フォーム トピック](../../mfc/form-views-mfc.md)を挿入することもできます。 アプリケーションで最初はフォームをサポートしていなかった場合でも、新しいフォームを挿入するときに、Visual C++ によってフォームのサポートが追加されます。

MFC アプリケーション ウィザードと [クラスの追加] コマンドは、フォーム ベースのアプリケーションを作成する方法として推奨されています。 これらのメソッドを使用せずにフォームベースのアプリケーションを作成する必要がある場合は、[フォームベースのアプリケーションの作成を](../../mfc/reference/creating-a-forms-based-mfc-application.md)参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

`CFormView`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxext.h

## <a name="cformviewcformview"></a><a name="cformview"></a>フォームビュー::フォームビュー

`CFormView` オブジェクトを構築します。

```
CFormView(LPCTSTR lpszTemplateName);
CFormView(UINT nIDTemplate);
```

### <a name="parameters"></a>パラメーター

*テンプレート名*<br/>
ダイアログ テンプレート リソースの名前である null で終わる文字列を格納します。

*テンプレート*<br/>
ダイアログ テンプレート リソースの ID 番号を格納します。

### <a name="remarks"></a>解説

派生`CFormView`した型のオブジェクトを作成する場合は、いずれかのコンストラクターを呼び出してビュー オブジェクトを作成し、ビューの基になるダイアログ リソースを識別します。 リソースは、名前 (コンストラクターの引数として文字列を渡す) または ID (引数として符号なし整数を渡す) によって識別できます。

フォーム ビュー ウィンドウと子コントロールは、呼び`CWnd::Create`出されるまで作成されません。 `CWnd::Create`は、ドキュメント テンプレートによって駆動されるドキュメントとビューの作成プロセスの一部として、フレームワークによって呼び出されます。

> [!NOTE]
> 派生クラスは、独自のコンストラクターを指定*する必要があります*。 コンストラクターで、前述のクラスの概要`CFormView::CFormView`に示すように、リソース名または ID を引数としてコンストラクター を呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#90](../../mfc/codesnippet/cpp/cformview-class_1.h)]

[!code-cpp[NVC_MFCDocView#91](../../mfc/codesnippet/cpp/cformview-class_2.cpp)]

## <a name="cformviewisinitdlgcompleted"></a><a name="isinitdlgcompleted"></a>フォームビュー::イシニトドアルグ完了

他の操作が実行される前に初期化が完了したことを確認するために MFC によって使用されます。

```
BOOL IsInitDlgCompleted() const;
```

### <a name="return-value"></a>戻り値

このダイアログの初期化関数が完了している場合は true。

## <a name="see-also"></a>関連項目

[MFC サンプル スナップVW](../../overview/visual-cpp-samples.md)<br/>
[MFC サンプル ビューレックス](../../overview/visual-cpp-samples.md)<br/>
[CScrollView クラス](../../mfc/reference/cscrollview-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/cdialog-class.md)<br/>
[CScrollView クラス](../../mfc/reference/cscrollview-class.md)
