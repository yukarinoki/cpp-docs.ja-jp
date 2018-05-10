---
title: 'TN017: ウィンドウ オブジェクトの破棄 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.objects
dev_langs:
- C++
helpviewer_keywords:
- destroying windows
- TN017
- PostNcDestroy method [MFC]
ms.assetid: 5bf208a5-5683-439b-92a1-547c5ded26cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c6bba255403d31e7a1fa03febb0c760d20cdc81c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="tn017-destroying-window-objects"></a>テクニカル ノート 17: ウィンドウ オブジェクトの破棄
このノートの使用法を説明する、 [:postncdestroy](../mfc/reference/cwnd-class.md#postncdestroy)メソッドです。 カスタマイズされた割り当てを実行する場合は、このメソッドを使用して`CWnd`-派生オブジェクト。 このノートで使用する理由について説明も[に](../mfc/reference/cwnd-class.md#destroywindow)の代わりに、C++ Windows オブジェクトを破棄する、`delete`演算子。  
  
 このトピックのガイドラインを行う場合は、いくつかのクリーンアップに関する問題があります。 削除/のようなシステム リソースを解放し忘れる C++ のメモリを解放し忘れるなどの問題からこれらの問題が生じる`HWND`、または回数が多すぎますオブジェクトを解放します。  
  
## <a name="the-problem"></a>問題を  
 各 windows オブジェクト (から派生したクラスのオブジェクト`CWnd`) C++ オブジェクトを表すと`HWND`です。 C++ オブジェクトでは、アプリケーションのヒープに割り当てられたおよび`HWND`ウィンドウ マネージャーによってシステム リソースに s が割り当てられます。 システムを回避するルールのセットを提供する必要がありますおウィンドウ オブジェクトを破棄するいくつかの方法があるため、リソースまたはメモリ リークが発生します。 オブジェクトおよび Windows ハンドルが複数回破棄されるおそれもする必要があります。  
  
## <a name="destroying-windows"></a>ウィンドウの破棄  
 Windows のオブジェクトを破棄する許可されている 2 つの方法を次に示します。  
  
-   呼び出す`CWnd::DestroyWindow`または Windows API`DestroyWindow`です。  
  
-   明示的に削除すると、`delete`演算子。  
  
 最初のケースが最も一般的です。 この場合は、コードが要求されていない場合でもは適用されます。`DestroyWindow`直接です。 ユーザーが直接フレーム ウィンドウを閉じたときにこの操作が生成されます、`WM_CLOSE`メッセージ、およびこのメッセージに既定の応答が呼び出されて`DestroyWindow.`親ウィンドウが破棄されるときに、Windows が呼び出す`DestroyWindow`すべての子です。  
  
 2 番目の場合、使用、`delete`演算子を Windows のオブジェクトには、まれである必要があります。 次を使用している場合も、`delete`オプションを選択します。  
  
## <a name="auto-cleanup-with-cwndpostncdestroy"></a>:Postncdestroy を使用して自動クリーンアップ  
 システムでは、Windows のウィンドウを破棄、ウィンドウに送信された最後の Windows メッセージは`WM_NCDESTROY`します。 既定値`CWnd`そのメッセージのハンドラーは、 [:onncdestroy](../mfc/reference/cwnd-class.md#onncdestroy)です。 `OnNcDestroy` デタッチは、 `HWND` C++ からオブジェクトし、仮想関数を呼び出す`PostNcDestroy`です。 一部のクラスは、C++ オブジェクトを削除するには、この関数をオーバーライドします。  
  
 既定の実装`CWnd::PostNcDestroy`ウィンドウ オブジェクトのスタック フレームに割り当てられた、またはその他のオブジェクトに埋め込まれているに最適な何もしません。 これは、他のオブジェクトのヒープに割り当てられるように設計されているウィンドウ オブジェクトを適していません。 つまり、他の C++ オブジェクトに埋め込まれていないウィンドウのオブジェクトの適切なは。  
  
 単独でヒープに割り当てられるように設計されているこれらのクラスでオーバーライド、`PostNcDestroy`メソッドを実行する、`delete this`です。 このステートメントは、C++ オブジェクトに関連付けられているメモリを解放します。 場合でも、既定`CWnd`デストラクター呼び出し`DestroyWindow`場合`m_hWnd`は NULL 以外の場合、これが発生しても無限再帰のハンドルになるため分離され、NULL がクリーンアップ フェーズ中にします。  
  
> [!NOTE]
>  通常、システムを呼び出します`CWnd::PostNcDestroy`、Windows を処理した後`WM_NCDESTROY`メッセージと`HWND`C++ ウィンドウ オブジェクトが不要になった接続されているとします。 システムは呼び出すことも`CWnd::PostNcDestroy`ほとんどの実装で[cwnd::create](../mfc/reference/cwnd-class.md#create)呼び出しエラーが発生した場合は。 自動クリーンアップ ルールは、このトピックの後で説明します。  
  
## <a name="auto-cleanup-classes"></a>自動クリーンアップ クラス  
 自動クリーンアップは、次のクラスは設計されていません。 値型は、通常の他の C++ オブジェクトか、またはスタックに埋め込まれます。  
  
-   すべての標準の Windows コントロール (`CStatic`、 `CEdit`、`CListBox`など)。  
  
-   すべての子ウィンドウから直接派生`CWnd`(たとえば、カスタム コントロール)。  
  
-   分割ウィンドウ (`CSplitterWnd`)。  
  
-   既定のコントロール バー (から派生したクラス`CControlBar`を参照してください[テクニカル ノート 31](../mfc/tn031-control-bars.md)コントロール バー オブジェクトの自動削除を有効にするため)。  
  
-   ダイアログ ボックス (`CDialog`) のスタック フレームにモーダル ダイアログ ボックス用に設計されています。  
  
-   除くすべての標準のダイアログ`CFindReplaceDialog`です。  
  
-   ClassWizard で作成された既定のダイアログ ボックス。  
  
 自動クリーンアップは、次のクラスは設計されています。 ヒープで自体によって通常割り当てられます。  
  
-   メイン フレーム ウィンドウ (から直接または間接的に派生`CFrameWnd`)。  
  
-   Windows の表示 (から直接または間接的に派生`CView`)。  
  
 これらの規則に違反する場合は、オーバーライドする必要があります、`PostNcDestroy`派生クラスのメソッドです。 クラスには、自動クリーンアップを追加するには基本クラスを呼び出すし、操作を行います、`delete this`です。 クラスから自動クリーンアップを削除するには、呼び出す`CWnd::PostNcDestroy`直接の代わりに、`PostNcDestroy`直接的な基底クラスのメソッドです。  
  
 自動クリーンアップの動作を変更した場合の最も一般的な用途では、ヒープに割り当てることができるモードレス ダイアログを作成します。  
  
## <a name="when-to-call-delete"></a>ときに呼び出しに削除する  
 呼び出すことをお勧め`DestroyWindow`を C++ メソッドまたはグローバルのいずれか、Windows のオブジェクトを破棄する`DestroyWindow`API です。  
  
 グローバル呼び出さない`DestroyWindow`MDI 子ウィンドウを破棄する API。 仮想メソッドを使用する必要があります`CWnd::DestroyWindow`代わりにします。  
  
 C++ ウィンドウ オブジェクトの自動クリーンアップを行わないを使用して、`delete`演算子を呼び出すしようとしたときにメモリ リークが発生できます`DestroyWindow`で、`CWnd::~CWnd`デストラクター、VTBL が正しく派生クラスを指していない場合。 これは、システムは、適切な破棄を呼び出すメソッドを見つけることが発生します。 使用して`DestroyWindow`の代わりに`delete`これらの問題を回避できます。 これは微妙なエラーなので、デバッグ モードでコンパイルすると、危険にさらされている場合に、次の警告が生成されます。  
  
```  
Warning: calling DestroyWindow in CWnd::~CWnd  
    OnDestroy or PostNcDestroy in derived class will not be called  
```  
  
 場合は、自動クリーンアップが実行されている C++ Windows オブジェクトを呼び出す必要があります`DestroyWindow`です。 使用する場合、`delete`演算子を直接 MFC 診断メモリ アロケーター通知をする 2 回、メモリが解放されます。 2 つのインスタンスは、最初の明示的な呼び出しおよびへの間接呼び出し`delete this`の自動クリーンアップの実装で`PostNcDestroy`です。  
  
 呼び出した後`DestroyWindow`、非自動クリーンアップ オブジェクトの C++ オブジェクトができます、周囲が`m_hWnd`は NULL になります。 呼び出した後`DestroyWindow`自動クリーンアップ オブジェクトに対して C++ オブジェクトはなくなっての自動クリーンアップの実装で C++ delete 演算子によって解放`PostNcDestroy`です。  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

