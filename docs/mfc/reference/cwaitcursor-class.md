---
title: CWaitCursor クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CWaitCursor
- AFXWIN/CWaitCursor
- AFXWIN/CWaitCursor::CWaitCursor
- AFXWIN/CWaitCursor::Restore
dev_langs:
- C++
helpviewer_keywords:
- CWaitCursor [MFC], CWaitCursor
- CWaitCursor [MFC], Restore
ms.assetid: 5dfae2ff-d7b6-4383-b0ad-91e0868c67b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e7bc4755d2e96c78735f1b3ef175ff3603686fb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33372509"
---
# <a name="cwaitcursor-class"></a>CWaitCursor クラス
時間がかかる処理を実行している最中に、通常は砂時計として表示される待機カーソルを表示する 1 つの方法を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CWaitCursor  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CWaitCursor::CWaitCursor](#cwaitcursor)|構築、`CWaitCursor`オブジェクトを待機カーソルを表示します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CWaitCursor::Restore](#restore)|変更された後に待機カーソルを復元します。|  
  
## <a name="remarks"></a>コメント  
 `CWaitCursor` 基本クラスはありません。  
  
 正確な Windows プログラミングでは、かなりの時間を取得する操作を実行するたびに待機カーソルを表示することが必要です。  
  
 待機カーソルを表示する定義だけ、`CWaitCursor`時間のかかる操作を実行するコードの前に変数。 オブジェクトのコンス トラクターは、自動的に表示される待機カーソルをによりします。  
  
 オブジェクトがスコープから外れとき (をブロックの最後に、`CWaitCursor`オブジェクトが宣言されている)、デストラクターは、以前のカーソルにカーソルを設定します。 つまり、オブジェクトは、必要なクリーンアップを自動的に実行します。  
  
> [!NOTE]
>  コンス トラクターとデストラクターの動作のため`CWaitCursor`オブジェクトは常にローカル変数として宣言: グローバル変数として宣言もで割り当てられている**新しい**です。  
  
 カーソルが、メッセージ ボックスまたはダイアログ ボックスで、呼び出しを表示するなど、変更する操作を実行する場合、[復元](#restore)待機カーソルを復元するメンバー関数。 呼び出すことが**復元**待機カーソルが表示されている場合でもです。  
  
 待機カーソルを表示する別の方法は、の組み合わせを使用する[CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor)、 [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)、そして[CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor). ただし、`CWaitCursor`時間のかかる操作を完了すると、以前のカーソルにカーソルを設定する必要がないために使用する方が簡単です。  
  
> [!NOTE]
>  MFC を設定し、カーソルを使用して、復元、 [CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor)仮想関数。 カスタム動作を提供するには、この関数をオーバーライドすることができます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CWaitCursor`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
## <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#62](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_1.cpp)]  
  
##  <a name="cwaitcursor"></a>  CWaitCursor::CWaitCursor  
 表示するには待機カーソルを宣言するだけ、`CWaitCursor`時間のかかる操作を実行するコードの前に、のオブジェクト。  
  
```  
CWaitCursor();
```  
  
### <a name="remarks"></a>コメント  
 コンス トラクターは、表示される待機カーソルを自動的にさせます。  
  
 オブジェクトがスコープから外れとき (をブロックの最後に、`CWaitCursor`オブジェクトが宣言されている)、デストラクターは、以前のカーソルにカーソルを設定します。 つまり、オブジェクトは、必要なクリーンアップを自動的に実行します。  
  
 そのデストラクターが呼び出される (可能性のある関数の終了前に)、ブロックの最後に、関数の部分のみで待機カーソルをアクティブにするのに事実を利用できます。 この方法は次の 2 番目の例に示します。  
  
> [!NOTE]
>  コンス トラクターとデストラクターの動作のため`CWaitCursor`オブジェクトは常にローカル変数として宣言など、グローバル変数として宣言もで割り当てられている**新しい**です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#63](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_2.cpp)]  
  
##  <a name="restore"></a>  CWaitCursor::Restore  
 待機カーソルを復元するには、メッセージ ボックスまたは待機カーソルを別のカーソルに変わることがあります ダイアログ ボックスを表示するなど、操作を実行した後、この関数を呼び出します。  
  
```  
void Restore();
```  
  
### <a name="remarks"></a>コメント  
 [Ok] を呼び出すことが**復元**待機カーソルが表示されている場合でもです。  
  
 1 つ以外の関数の中に待機カーソルを復元する必要がある場合、`CWaitCursor`を呼び出して、オブジェクトが宣言されている[CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#64](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_3.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor)   
 [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)   
 [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)   
 [CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor)   
 [I: はマウス カーソルを Microsoft Foundation クラスのアプリケーションに変更する方法](http://go.microsoft.com/fwlink/p/?linkid=128044)



