---
title: CMultiDocTemplate クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMultiDocTemplate
- AFXWIN/CMultiDocTemplate
- AFXWIN/CMultiDocTemplate::CMultiDocTemplate
dev_langs:
- C++
helpviewer_keywords:
- CMultiDocTemplate [MFC], CMultiDocTemplate
ms.assetid: 5b8aa328-e461-41d0-b388-00594535e119
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7b53228b6983c0293eb288cd0f38669d1b5db928
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
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
|[CMultiDocTemplate::CMultiDocTemplate](#cmultidoctemplate)|`CMultiDocTemplate` オブジェクトを構築します。|  
  
## <a name="remarks"></a>コメント  
 MDI アプリケーションでは、ドキュメントを表示する各ユーザーが 0 個以上のドキュメント フレーム ウィンドウを開くことができますのワークスペースとメイン フレーム ウィンドウを使用します。 MDI のより詳細な説明を参照してください。*ソフトウェア設計のための Windows インターフェイス ガイドライン*です。  
  
 ドキュメント テンプレートには、3 種類のクラス間のリレーションシップを定義します。  
  
-   派生するドキュメント クラス[CDocument](../../mfc/reference/cdocument-class.md)です。  
  
-   ビュー クラス上に示したドキュメント クラスのデータを表示します。 このクラスから派生できます[CView](../../mfc/reference/cview-class.md)、 `CScrollView`、 `CFormView`、または`CEditView`です。 (使用することも`CEditView`直接)。  
  
-   ビューを含むフレーム ウィンドウ クラスです。 MDI ドキュメント テンプレートからこのクラスを派生できます`CMDIChildWnd`、または、使用することができる場合、ドキュメント フレーム ウィンドウの動作をカスタマイズする必要はありません、 [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)独自のクラスを派生することがなく、直接です。  
  
 MDI アプリケーションは、ドキュメントの 1 つ以上の型をサポートできるし、同時に異なる種類のドキュメントを開くことができます。 アプリケーションでは、各ドキュメントの種類はサポートしている 1 つのドキュメント テンプレートを持ちます。 たとえば、MDI アプリケーションでは、スプレッドシートやテキスト ドキュメントの両方をサポートする場合、アプリケーションが 2 つ`CMultiDocTemplate`オブジェクト。  
  
 アプリケーションは、ユーザーが新しいドキュメントを作成するときに、ドキュメント テンプレートを使用します。 アプリケーションでは、ドキュメントの 1 つ以上の型をサポートするフレームワークはドキュメント テンプレートからサポートされているドキュメントの種類の名前を取得し、新しいファイル ダイアログ ボックスの一覧に表示されます。 ユーザーがドキュメントの種類を選択すると、アプリケーションがドキュメント クラスのオブジェクト、フレーム ウィンドウ オブジェクト、およびビューのオブジェクトを作成し、それらを相互に接続します。  
  
 任意のメンバーの関数を呼び出す必要はありません`CMultiDocTemplate`コンス トラクターを除きます。 Framework ハンドル`CMultiDocTemplate`オブジェクトを内部的にします。  
  
 詳細については`CMultiDocTemplate`を参照してください[ドキュメント テンプレートとドキュメント/ビューの作成手順](../../mfc/document-templates-and-the-document-view-creation-process.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)  
  
 `CMultiDocTemplate`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="cmultidoctemplate"></a>  CMultiDocTemplate::CMultiDocTemplate  
 `CMultiDocTemplate` オブジェクトを構築します。  
  
```  
CMultiDocTemplate(
    UINT nIDResource,  
    CRuntimeClass* pDocClass,  
    CRuntimeClass* pFrameClass,  
    CRuntimeClass* pViewClass);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDResource`  
 ドキュメントの種類で使用するリソースの ID を指定します。 これには、メニューのアイコン、アクセラレータ テーブル、および文字列リソースが含まれます。  
  
 文字列リソースは、'\n' 文字で区切られた最大 7 つの部分文字列で構成されます (部分文字列が含まれていない場合、プレース ホルダーとして '\n' 文字が必要ですただし、末尾の '\n' 文字は必要ありません;)。これらの部分文字列では、ドキュメントの種類について説明します。 詳細については、部分文字列は、次を参照してください。 [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring)です。 この文字列リソースについては、アプリケーションのリソース ファイルにあります。 例えば:  
  
 `// MYCALC.RC`  
  
 `STRINGTABLE PRELOAD DISCARDABLE`  
  
 `BEGIN`  
  
 `IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"`  
  
 `END`  
  
 文字列は"\n"文字で始まることに注意してください。これは、最初の部分文字列が MDI アプリケーションで実行されていない、したがってが含まれていないためです。 ストリング エディターを使用してこの文字列を編集することができます。文字列全体は、7 つの独立したエントリとしてではなく文字列エディターで、1 つのエントリとして表示されます。  
  
 これらのリソースの種類の詳細については、次を参照してください。[リソース エディター](../../windows/resource-editors.md)です。  
  
 `pDocClass`  
 指す、`CRuntimeClass`ドキュメント クラスのオブジェクト。 このクラスは、 **CDocument**のドキュメントを表すために定義するクラスを派生します。  
  
 `pFrameClass`  
 指す、`CRuntimeClass`フレーム ウィンドウ クラスのオブジェクト。 このクラスにすることができます、 `CMDIChildWnd`-派生クラスにすることもできます`CMDIChildWnd`自体、ドキュメント フレーム ウィンドウの既定の動作をする場合。  
  
 `pViewClass`  
 指す、`CRuntimeClass`ビュー クラスのオブジェクト。 このクラスは、 `CView`-、ドキュメントを表示を定義するクラスを派生します。  
  
### <a name="remarks"></a>コメント  
 いずれかを動的に割り当てる`CMultiDocTemplate`各ドキュメントの種類、アプリケーションをサポートし、それぞれを渡すオブジェクト`CWinApp::AddDocTemplate`から、`InitInstance`アプリケーション クラスのメンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#92](../../mfc/codesnippet/cpp/cmultidoctemplate-class_1.cpp)]  
  
 2 番目の例を次に示します。  
  
 [!code-cpp[NVC_MFCDocView#93](../../mfc/codesnippet/cpp/cmultidoctemplate-class_2.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)   
 [関数クラス](../../mfc/reference/csingledoctemplate-class.md)   
 [CWinApp クラス](../../mfc/reference/cwinapp-class.md)
