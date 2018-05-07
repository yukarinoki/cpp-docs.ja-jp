---
title: CCreateContext 構造 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCreateContext
dev_langs:
- C++
helpviewer_keywords:
- CCreateContext structure [MFC]
ms.assetid: 337a0e44-d910-49a8-afc0-c7207666a9dc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: af6e81b9215aa6e7bc9e5f294a1d95aee4b51321
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="ccreatecontext-structure"></a>CCreateContext 構造体
フレームワークを使用して、`CCreateContext`フレーム ウィンドウとドキュメントに関連付けられているビューの作成時に構造体します。  
  
## <a name="syntax"></a>構文  
  
```  
struct CCreateContext  
```  
  
## <a name="remarks"></a>コメント  
 `CCreateContext` 構造体は、基本クラスではありません。  
  
 ウィンドウを作成するときに、この構造体の値は、そのデータのビューに、ドキュメントのコンポーネントを接続するために使用情報を提供します。 のみを使用する必要がある`CCreateContext`作成プロセスの一部をオーバーライドする場合。  
  
 A`CCreateContext`構造には、ドキュメント、フレーム ウィンドウ、ビュー、およびドキュメント テンプレートへのポインターが含まれています。 ポインターも含まれています、`CRuntimeClass`を作成するビューの種類を識別します。 ランタイム クラス情報と現在のドキュメント ポインターは、動的に新しいビューの作成に使用されます。 次の表は、時期と方法を提案各`CCreateContext`メンバーを使用する場合があります。  
  
|メンバー|型|何が|  
|------------|----------|--------------------|  
|`m_pNewViewClass`|`CRuntimeClass*`|`CRuntimeClass` 新しいビューを作成します。|  
|`m_pCurrentDoc`|`CDocument*`|新しいビューに関連する既存のドキュメントです。|  
|`m_pNewDocTemplate`|`CDocTemplate*`|新しい MDI フレーム ウィンドウの作成に関連付けられているドキュメント テンプレートです。|  
|`m_pLastView`|`CView*`|元のビューを他のビューは、モデル化、分割ウィンドウのビューの作成またはドキュメント上の 2 つ目のビューの作成と同様にします。|  
|`m_pCurrentFrame`|`CFrameWnd*`|フレーム ウィンドウを追加のフレーム ウィンドウは、モデル化、ドキュメントの 2 番目のフレーム ウィンドウの作成と同様にします。|  
  
 格納された情報を検証するドキュメント テンプレートは、ドキュメントとその関連コンポーネントを作成するとき、`CCreateContext`構造体。 たとえば、存在しないドキュメントのビューを作成できません必要があります。  
  
> [!NOTE]
>  すべてのポインターの`CCreateContext`は省略可能であり`NULL`指定されていないか不明な場合です。  
  
 `CCreateContext` 下に表示するメンバー関数によって使用される「ご覧ください」。 これらをオーバーライドする場合に、特定の情報をこれらの関数の説明を参照してください。  
  
 次に、いくつかの一般的なガイドラインを示します。  
  
-   ウィンドウを作成するための引数として渡されるときに`CWnd::Create`、 `CFrameWnd::Create`、および`CFrameWnd::LoadFrame`、作成コンテキストでは、どのような新しいウィンドウに接続を指定します。 ほとんどの windows では、全体の構造は省略可能、および`NULL`ポインターを渡すことができます。  
  
-   オーバーライド可能なメンバー関数の場合など、 `CFrameWnd::OnCreateClient`、`CCreateContext`引数は省略可能です。  
  
-   メンバー関数の関連するビューで作成、入力してください、ビューを作成するための十分な情報。 たとえば、最初のビューの分割ウィンドウで クラスの情報を表示し、現在のドキュメントを指定してください。  
  
 一般に、フレームワークの既定値を使用する場合、無視してかまいません`CCreateContext`です。 高度な変更、Microsoft Foundation Class ライブラリのソース コードまたは VIEWEX などのサンプル プログラムしようとすると、説明します。 必須のパラメーターを忘れると、フレームワーク アサートされ、忘れた場合が送信されます。  
  
 詳細については`CCreateContext`、MFC サンプルを参照して[VIEWEX](../../visual-cpp-samples.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxext.h  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFrameWnd::Create](../../mfc/reference/cframewnd-class.md#create)   
 [CFrameWnd::LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe)   
 [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)   
 [CSplitterWnd::Create](../../mfc/reference/csplitterwnd-class.md#create)   
 [CSplitterWnd::CreateView](../../mfc/reference/csplitterwnd-class.md#createview)   
 [CWnd::Create](../../mfc/reference/cwnd-class.md#create)

