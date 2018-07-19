---
title: CFormView クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFormView
- AFXEXT/CFormView
- AFXEXT/CFormView::CFormView
- AFXEXT/CFormView::IsInitDlgCompleted
dev_langs:
- C++
helpviewer_keywords:
- CFormView [MFC], CFormView
- CFormView [MFC], IsInitDlgCompleted
ms.assetid: a99ec313-36f0-4f28-9d2b-de11de14ac19
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aa06581dc28293073e8094dad779be0eebabbd10
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953491"
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
  
## <a name="remarks"></a>Remarks  
 フォーム ビューは、基本的には、コントロールを含むビューです。 これらのコントロールは、ダイアログ テンプレート リソースに基づいて配置されます。 アプリケーションでフォームが必要な場合は、`CFormView` を使用します。 これらのビューをサポートして、スクロールを使用して、必要に応じて、 [CScrollView](../../mfc/reference/cscrollview-class.md)機能します。  
  
 できたら[フォーム ベースのアプリケーションを作成する](../../mfc/reference/creating-a-forms-based-mfc-application.md)、そのビュー クラスの基`CFormView`、フォーム ベースのアプリケーションを作成します。  
  
 挿入することも新しい[フォームに関するトピック](../../mfc/form-views-mfc.md)ドキュメント ビュー ベースのアプリケーションにします。 アプリケーションで最初はフォームをサポートしていなかった場合でも、新しいフォームを挿入するときに、Visual C++ によってフォームのサポートが追加されます。  
  
 MFC アプリケーション ウィザードと [クラスの追加] コマンドは、フォーム ベースのアプリケーションを作成する方法として推奨されています。 これらのメソッドを使用せずにフォーム ベースのアプリケーションを作成、表示する必要がある場合[フォーム ベースのアプリケーションを作成する](../../mfc/reference/creating-a-forms-based-mfc-application.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 `CFormView`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxext.h  
  
##  <a name="cformview"></a>  CFormView::CFormView  
 `CFormView` オブジェクトを構築します。  
  
```  
CFormView(LPCTSTR lpszTemplateName);  
CFormView(UINT nIDTemplate);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszTemplateName*  
 ダイアログ テンプレート リソースの名前を指定する null で終わる文字列が含まれています。  
  
 *nIDTemplate*  
 ダイアログ テンプレート リソースの ID 番号が含まれています。  
  
### <a name="remarks"></a>Remarks  
 派生した型のオブジェクトを作成するときに`CFormView`、ビュー オブジェクトを作成し、ビューの基になるダイアログ リソースを識別するコンス トラクターの 1 つを呼び出します。 名前 (コンス トラクターの引数として文字列を渡す) で、または ID (パスを符号なし整数の引数として) では、リソースを識別できます。  
  
 まで、フォーム ビュー ウィンドウおよび子コントロールを作成しない`CWnd::Create`と呼びます。 `CWnd::Create` ドキュメント テンプレートによりドキュメントとビューの作成プロセスの一環としてフレームワークによって呼び出されます。  
  
> [!NOTE]
>  派生クラス*必要があります*独自のコンス トラクターを指定します。 コンス トラクターを呼び出すのコンス トラクターで`CFormView::CFormView`リソース名または ID を上記のクラスの概要で示すように引数として使用します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#90](../../mfc/codesnippet/cpp/cformview-class_1.h)]  
  
 [!code-cpp[NVC_MFCDocView#91](../../mfc/codesnippet/cpp/cformview-class_2.cpp)]  
  
##  <a name="isinitdlgcompleted"></a>  CFormView::IsInitDlgCompleted  
 他の操作が実行される前に初期化が完了したことを確認するために MFC によって使用されます。  
  
```  
BOOL IsInitDlgCompleted() const;  
```  
  
### <a name="return-value"></a>戻り値  
 このダイアログの初期化関数が完了している場合は true。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル SNAPVW](../../visual-cpp-samples.md)   
 [MFC サンプル VIEWEX](../../visual-cpp-samples.md)   
 [CScrollView クラス](../../mfc/reference/cscrollview-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDialog クラス](../../mfc/reference/cdialog-class.md)   
 [CScrollView クラス](../../mfc/reference/cscrollview-class.md)
