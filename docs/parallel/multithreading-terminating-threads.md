---
title: マルチ スレッド。MFC でのスレッドの終了
ms.date: 08/27/2018
f1_keywords:
- CREATE_SUSPENDED
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
ms.openlocfilehash: dd11f5db646e172d7ea2c2cc646841249d95ef31
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57303632"
---
# <a name="multithreading-terminating-threads-in-mfc"></a>マルチ スレッド。MFC でのスレッドの終了

通常、スレッドは、次の 2 つの条件で終了します。1 つは制御関数が終了した場合、もう 1 つはスレッドを最後まで実行できなかった場合です。 ワード プロセッサでバックグラウンド印刷用のスレッドを使っている場合、印刷が正常に終了すると、制御関数が正常に終了します。 ただし、ユーザーが印刷をキャンセルするときは、バッググラウンド印刷用のスレッドを途中で終了する必要があります。 このトピックでは、この 2 つの終了処理を実現する方法と、スレッド終了時の終了コードを取得する方法について説明します。

- [スレッドの正常終了](#_core_normal_thread_termination)

- [スレッドの中断](#_core_premature_thread_termination)

- [スレッドの終了コードを取得します。](#_core_retrieving_the_exit_code_of_a_thread)

##  <a name="_core_normal_thread_termination"></a> スレッドの正常終了

ワーカー スレッドのスレッドの正常終了は単純です。制御関数を終了し、終了の理由を示す値を返します。 いずれかを使用することができます、 [AfxEndThread](../mfc/reference/application-information-and-management.md#afxendthread)関数または**返す**ステートメント。 通常、0 を返して正常終了を通知しますが、返す値はプログラマが決めることができます。

ユーザー インターフェイス スレッドでは、そのプロセスは同じように簡単: から、ユーザー インターフェイス スレッド内で呼び出す[PostQuitMessage](/windows/desktop/api/winuser/nf-winuser-postquitmessage) Windows SDK に含まれています。 唯一のパラメーターを`PostQuitMessage`受け取りますが、スレッドの終了コード。 ワーカー スレッドの場合と同じように、通常は 0 を返して正常終了を通知します。

##  <a name="_core_premature_thread_termination"></a> スレッドの中断

スレッドの中断は、シンプルには。呼び出す[AfxEndThread](../mfc/reference/application-information-and-management.md#afxendthread)から、スレッド内で。 パラメーターは終了コードだけです。 この関数はスレッドの実行を停止し、スレッドが占有していたスタック領域を解放し、スレッドにアタッチしているすべての DLL をデタッチし、メモリからスレッド オブジェクトを削除します。

関数 `AfxEndThread` は終了するスレッドから呼び出します。 あるスレッドを別のスレッドから終了させるには、2 つのスレッド間の通信メソッドを設定する必要があります。

##  <a name="_core_retrieving_the_exit_code_of_a_thread"></a> スレッドの終了コードを取得します。

ワーカーまたはユーザー インターフェイス スレッドの終了コードを取得する、 [GetExitCodeThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getexitcodethread)関数。 この関数については、Windows SDK を参照してください。 この関数は、スレッド ハンドルを受け取ります (に格納されている、`m_hThread`データ メンバーの`CWinThread`オブジェクト) と、DWORD のアドレス。

場合は、スレッドがアクティブで`GetExitCodeThread`STILL_ACTIVE に指定された DWORD アドレス配置このアドレスに終了コードを配置する場合は、します。

終了コードを取得する[CWinThread](../mfc/reference/cwinthread-class.md)オブジェクトは余分な手順です。 既定では、`CWinThread` スレッドが終了すると、このスレッド オブジェクトが削除されます。 つまり、`m_hThread` オブジェクトがもう存在しないので、`CWinThread` データ メンバーにはアクセスできません。 この状況を回避するには、以下のいずれかの操作を実行します。

- 設定、`m_bAutoDelete`データ メンバーを FALSE にします。 これにより、`CWinThread` オブジェクトは、スレッドが終了した後も残ります。 次に、スレッドが終了した後で、`m_hThread` データ メンバーにアクセスできます。 ただし、この方法を使用すると、フレームワークでは `CWinThread` オブジェクトが自動的に削除されないため、このオブジェクトを直接破棄する必要があります。 この方法をお勧めします。

- スレッドへのハンドルを別に保存します。 スレッドが作成されると、コピー、`m_hThread`データ メンバー (を使用して`::DuplicateHandle`) 別の変数にし、その変数を通じてアクセスします。 この方法では、スレッドの終了時にオブジェクトが自動的に削除され、スレッドが終了した理由もわかります。 この場合、スレッドを終了しないと、ハンドルを複製できません。 これを行うに最も安全な方法に CREATE_SUSPENDED を渡す[AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread)、ハンドルを格納し、呼び出すことによって、スレッドを再開、 [ResumeThread](../mfc/reference/cwinthread-class.md#resumethread)します。

この方法のどちらかを使うと、`CWinThread` オブジェクトの終了理由を判定できます。

## <a name="see-also"></a>関連項目

[C++ と MFC を使用するマルチスレッド](multithreading-with-cpp-and-mfc.md)<br/>
[_endthread、_endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)<br/>
[_beginthread、_beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)<br/>
[ExitThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-exitthread)
