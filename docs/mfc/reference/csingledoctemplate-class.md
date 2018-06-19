---
title: 関数クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSingleDocTemplate
- AFXWIN/CSingleDocTemplate
- AFXWIN/CSingleDocTemplate::CSingleDocTemplate
dev_langs:
- C++
helpviewer_keywords:
- CSingleDocTemplate [MFC], CSingleDocTemplate
ms.assetid: 4f3a8212-81ee-48a0-ad22-e0ed7c36a391
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 413b7b4a7cf11ff7e83596ecc61423d4bc4f0358
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371622"
---
# <a name="csingledoctemplate-class"></a>関数クラス
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
  
## <a name="remarks"></a>コメント  
 SDI アプリケーションでは、メイン フレーム ウィンドウを使用して、ドキュメントを表示1 つだけのドキュメントは、一度に開くことができます。  
  
 ドキュメント テンプレートには、3 種類のクラス間のリレーションシップを定義します。  
  
-   派生するドキュメント クラス**CDocument**です。  
  
-   ビュー クラス上に示したドキュメント クラスのデータを表示します。 このクラスから派生できます`CView`、 `CScrollView`、 `CFormView`、または`CEditView`です。 (使用することも`CEditView`直接)。  
  
-   ビューを含むフレーム ウィンドウ クラスです。 SDI ドキュメント テンプレートからこのクラスを派生できます`CFrameWnd`以外のかどうかは、メインの動作をカスタマイズする必要はありませんフレーム ウィンドウは、使用できます`CFrameWnd`独自のクラスを派生することがなく、直接です。  
  
 SDI アプリケーション通常をサポートしている 1 つの種類のドキュメントを 1 つだけがあるため`CSingleDocTemplate`オブジェクト。 1 つだけのドキュメントは、一度に開くことができます。  
  
 任意のメンバーの関数を呼び出す必要はありません`CSingleDocTemplate`コンス トラクターを除きます。 Framework ハンドル`CSingleDocTemplate`オブジェクトを内部的にします。  
  
 使用する方法についての`CSingleDocTemplate`を参照してください[ドキュメント テンプレートとドキュメント/ビューの作成手順](../../mfc/document-templates-and-the-document-view-creation-process.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)  
  
 `CSingleDocTemplate`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="csingledoctemplate"></a>  CSingleDocTemplate::CSingleDocTemplate  
 `CSingleDocTemplate` オブジェクトを構築します。  
  
```  
CSingleDocTemplate(
    UINT nIDResource,  
    CRuntimeClass* pDocClass,  
    CRuntimeClass* pFrameClass,  
    CRuntimeClass* pViewClass);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDResource`  
 ドキュメントの種類で使用するリソースの ID を指定します。 これには、メニューのアイコン、アクセラレータ テーブル、および文字列リソースが含まれます。  
  
 文字列リソースは、'\n' 文字で区切られた最大 7 つの部分文字列で構成されます (部分文字列が含まれていない場合、プレース ホルダーとして '\n' 文字が必要ですただし、末尾の '\n' 文字は必要ありません;)。これらの部分文字列では、ドキュメントの種類について説明します。 部分文字列の詳細については、次を参照してください。 [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring)です。 この文字列リソースについては、アプリケーションのリソース ファイルにあります。 例えば:  
  
 `// MYCALC.RC`  
  
 `STRINGTABLE PRELOAD DISCARDABLE`  
  
 `BEGIN`  
  
 `IDR_MAINFRAME "MyCalc Windows Application\nSheet\nWorksheet\n Worksheets (*.myc)\n.myc\nMyCalcSheet\n MyCalc Worksheet"`  
  
 `END`  
  
 ストリング エディターを使用してこの文字列を編集することができます。文字列全体は、7 つの独立したエントリとしてではなく文字列エディターで、1 つのエントリとして表示されます。  
  
 これらのリソースの種類の詳細については、次を参照してください。、[ストリング エディター](../../windows/string-editor.md)です。  
  
 `pDocClass`  
 指す、`CRuntimeClass`ドキュメント クラスのオブジェクト。 このクラスは、 **CDocument**のドキュメントを表すために定義するクラスを派生します。  
  
 `pFrameClass`  
 指す、`CRuntimeClass`フレーム ウィンドウ クラスのオブジェクト。 このクラスにすることができます、 `CFrameWnd`-派生クラスにすることもできます`CFrameWnd`自体、メイン フレーム ウィンドウの既定の動作をする場合。  
  
 `pViewClass`  
 指す、`CRuntimeClass`ビュー クラスのオブジェクト。 このクラスは、 `CView`-、ドキュメントを表示を定義するクラスを派生します。  
  
### <a name="remarks"></a>コメント  
 動的に割り当てる、`CSingleDocTemplate`オブジェクトに渡すと`CWinApp::AddDocTemplate`から、`InitInstance`アプリケーション クラスのメンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocViewSDI#13](../../mfc/codesnippet/cpp/csingledoctemplate-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCDocViewSDI#14](../../mfc/codesnippet/cpp/csingledoctemplate-class_2.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル DOCKTOOL](../../visual-cpp-samples.md)   
 [CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)   
 [CDocument クラス](../../mfc/reference/cdocument-class.md)   
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)   
 [CMultiDocTemplate クラス](../../mfc/reference/cmultidoctemplate-class.md)   
 [CView クラス](../../mfc/reference/cview-class.md)   
 [CWinApp クラス](../../mfc/reference/cwinapp-class.md)
