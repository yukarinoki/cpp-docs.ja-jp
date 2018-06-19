---
title: 'マルチ スレッド: スレッドの終了 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
f1_keywords:
- CREATE_SUSPENDED
dev_langs:
- C++
helpviewer_keywords:
- premature thread termination
- starting threads
- threading [MFC], terminating threads
- multithreading [C++], terminating threads
- threading [C++], stopping threads
- terminating threads
- stopping threads
- AfxEndThread method
ms.assetid: 4c0a8c6d-c02f-456d-bd02-0a8c8d006ecb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bdf9376e9f8c9e9d74d88d0bef40dc71fd43d51f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33689585"
---
# <a name="multithreading-terminating-threads"></a>マルチスレッド : スレッドの終了
通常、スレッドは、次の 2 つの条件で終了します。1 つは制御関数が終了した場合、もう 1 つはスレッドを最後まで実行できなかった場合です。 ワード プロセッサでバックグラウンド印刷用のスレッドを使っている場合、印刷が正常に終了すると、制御関数が正常に終了します。 ただし、ユーザーが印刷をキャンセルするときは、バッググラウンド印刷用のスレッドを途中で終了する必要があります。 このトピックでは、この 2 つの終了処理を実現する方法と、スレッド終了時の終了コードを取得する方法について説明します。  
  
-   [スレッドの正常終了](#_core_normal_thread_termination)  
  
-   [スレッドの中断](#_core_premature_thread_termination)  
  
-   [スレッドの終了コードを取得します。](#_core_retrieving_the_exit_code_of_a_thread)  
  
##  <a name="_core_normal_thread_termination"></a> スレッドの正常終了  
 ワーカー スレッドでは、スレッドの正常終了は単純です。制御関数を終了し、終了理由を呼び出し元に返すだけです。 使用するか、 [AfxEndThread](../mfc/reference/application-information-and-management.md#afxendthread)関数または`return`ステートメントです。 通常、0 を返して正常終了を通知しますが、返す値はプログラマが決めることができます。  
  
 ユーザー インターフェイス スレッド、プロセスは同じように簡単: からユーザー インターフェイス スレッド内で呼び出す[PostQuitMessage](http://msdn.microsoft.com/library/windows/desktop/ms644945)で、[!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]です。 唯一のパラメーターを**PostQuitMessage**受け取りますが、スレッドの終了コード。 ワーカー スレッドの場合と同じように、通常は 0 を返して正常終了を通知します。  
  
##  <a name="_core_premature_thread_termination"></a> スレッドの中断  
 同じくらい簡単には、スレッドの処理の途中で終了: 呼び出す[AfxEndThread](../mfc/reference/application-information-and-management.md#afxendthread)からスレッド内で。 パラメーターは終了コードだけです。 この関数はスレッドの実行を停止し、スレッドが占有していたスタック領域を解放し、スレッドにアタッチしているすべての DLL をデタッチし、メモリからスレッド オブジェクトを削除します。  
  
 関数 `AfxEndThread` は終了するスレッドから呼び出します。 あるスレッドを別のスレッドから終了させるには、2 つのスレッド間の通信メソッドを設定する必要があります。  
  
##  <a name="_core_retrieving_the_exit_code_of_a_thread"></a> スレッドの終了コードを取得します。  
 ワーカーまたはユーザー インターフェイス スレッドの終了コードを取得する、 [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190)関数。 この関数については、[!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)] を参照してください。 この関数は、`m_hThread` オブジェクトの `CWinThread` データ メンバーに格納されている、スレッドへのハンドルと、`DWORD` のアドレスを取ります。  
  
 スレッドがアクティブである場合**GetExitCodeThread**配置**STILL_ACTIVE** 、示された`DWORD`アドレスです。 それ以外の場合、終了コードは、このアドレスに配置されます。  
  
 終了コードを取得する[CWinThread](../mfc/reference/cwinthread-class.md)オブジェクトは余分な手順です。 既定では、`CWinThread` スレッドが終了すると、このスレッド オブジェクトが削除されます。 つまり、`m_hThread` オブジェクトがもう存在しないので、`CWinThread` データ メンバーにはアクセスできません。 この状況を回避するには、以下のいずれかの操作を実行します。  
  
-   設定、`m_bAutoDelete`データ メンバーを**FALSE**です。 これにより、`CWinThread` オブジェクトは、スレッドが終了した後も残ります。 次に、スレッドが終了した後で、`m_hThread` データ メンバーにアクセスできます。 ただし、この方法を使用すると、フレームワークでは `CWinThread` オブジェクトが自動的に削除されないため、このオブジェクトを直接破棄する必要があります。 この方法をお勧めします。  
  
-   スレッドへのハンドルを別に保存します。 スレッドが作成された後、コピー、`m_hThread`データ メンバー (を使用して **:::duplicatehandle**) 別の変数にし、その変数を使用してアクセスします。 この方法では、スレッドの終了時にオブジェクトが自動的に削除され、スレッドが終了した理由もわかります。 この場合、スレッドを終了しないと、ハンドルを複製できません。 これを行う最も安全な方法に渡す**CREATE_SUSPENDED**に[AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread)、ハンドルを格納、およびを呼び出してスレッドを再開[ResumeThread](../mfc/reference/cwinthread-class.md#resumethread)です。  
  
 この方法のどちらかを使うと、`CWinThread` オブジェクトの終了理由を判定できます。  
  
## <a name="see-also"></a>関連項目  
 [C++ と MFC を使用するマルチ スレッド](../parallel/multithreading-with-cpp-and-mfc.md)   
 [_endthread、_endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)   
 [_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)   
 [ExitThread](http://msdn.microsoft.com/library/windows/desktop/ms682659)