---
title: 'マルチスレッド: MFC でのスレッドの終了'
ms.date: 08/27/2018
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
ms.openlocfilehash: 0625be0a628a6ae991acd2fa1f7118a4deabccda
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217871"
---
# <a name="multithreading-terminating-threads-in-mfc"></a>マルチスレッド: MFC でのスレッドの終了

通常、スレッドは、次の 2 つの条件で終了します。1 つは制御関数が終了した場合、もう 1 つはスレッドを最後まで実行できなかった場合です。 ワード プロセッサでバックグラウンド印刷用のスレッドを使っている場合、印刷が正常に終了すると、制御関数が正常に終了します。 ただし、ユーザーが印刷をキャンセルするときは、バッググラウンド印刷用のスレッドを途中で終了する必要があります。 このトピックでは、この 2 つの終了処理を実現する方法と、スレッド終了時の終了コードを取得する方法について説明します。

- [スレッドの正常終了](#_core_normal_thread_termination)

- [スレッドの中断](#_core_premature_thread_termination)

- [スレッドの終了コードの取得](#_core_retrieving_the_exit_code_of_a_thread)

## <a name="normal-thread-termination"></a><a name="_core_normal_thread_termination"></a>通常のスレッドの終了

ワーカー スレッドでは、スレッドの正常終了は単純です。制御関数を終了し、終了理由を呼び出し元に返すだけです。 [AfxEndThread](../mfc/reference/application-information-and-management.md#afxendthread)関数またはステートメントのいずれかを使用でき **`return`** ます。 通常、0 を返して正常終了を通知しますが、返す値はプログラマが決めることができます。

ユーザーインターフェイススレッドの場合、プロセスは単に単純です。ユーザーインターフェイススレッド内から、Windows SDK で[PostQuitMessage](/windows/win32/api/winuser/nf-winuser-postquitmessage)を呼び出します。 が取る唯一のパラメーター `PostQuitMessage` は、スレッドの終了コードです。 ワーカー スレッドの場合と同じように、通常は 0 を返して正常終了を通知します。

## <a name="premature-thread-termination"></a><a name="_core_premature_thread_termination"></a>スレッドの途中終了

スレッドを途中で終了するのは、スレッド内から[AfxEndThread](../mfc/reference/application-information-and-management.md#afxendthread)を呼び出すとほぼ単純です。 パラメーターは終了コードだけです。 この関数はスレッドの実行を停止し、スレッドが占有していたスタック領域を解放し、スレッドにアタッチしているすべての DLL をデタッチし、メモリからスレッド オブジェクトを削除します。

関数 `AfxEndThread` は終了するスレッドから呼び出します。 あるスレッドを別のスレッドから終了させるには、2 つのスレッド間の通信メソッドを設定する必要があります。

## <a name="retrieving-the-exit-code-of-a-thread"></a><a name="_core_retrieving_the_exit_code_of_a_thread"></a>スレッドの終了コードを取得する

ワーカースレッドまたはユーザーインターフェイススレッドの終了コードを取得するには、 [GetExitCodeThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodethread)関数を呼び出します。 この関数の詳細については、Windows SDK を参照してください。 この関数は、(オブジェクトのデータメンバーに格納されている) スレッドへのハンドル `m_hThread` `CWinThread` と、DWORD のアドレスを受け取ります。

スレッドがアクティブな場合は、 `GetExitCodeThread` 指定された DWORD アドレスに STILL_ACTIVE を配置します。それ以外の場合は、終了コードをこのアドレスに配置します。

[CWinThread](../mfc/reference/cwinthread-class.md)オブジェクトの終了コードを取得するには、追加の手順を実行します。 既定では、`CWinThread` スレッドが終了すると、このスレッド オブジェクトが削除されます。 つまり、`m_hThread` オブジェクトがもう存在しないので、`CWinThread` データ メンバーにはアクセスできません。 この状況を回避するには、以下のいずれかの操作を実行します。

- `m_bAutoDelete`データメンバーを FALSE に設定します。 これにより、`CWinThread` オブジェクトは、スレッドが終了した後も残ります。 次に、スレッドが終了した後で、`m_hThread` データ メンバーにアクセスできます。 ただし、この方法を使用すると、フレームワークでは `CWinThread` オブジェクトが自動的に削除されないため、このオブジェクトを直接破棄する必要があります。 可能であればこの方法の使用をお勧めします。

- スレッドへのハンドルを別に保存します。 スレッドが作成されたら、その `m_hThread` データメンバー (を使用 `::DuplicateHandle` ) を別の変数にコピーし、その変数を使用してアクセスします。 この方法では、スレッドの終了時にオブジェクトが自動的に削除され、スレッドが終了した理由もわかります。 この場合、スレッドを終了しないと、ハンドルを複製できません。 これを実行する最も安全な方法は、CREATE_SUSPENDED を[AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread)に渡し、ハンドルを格納した後、 [ResumeThread](../mfc/reference/cwinthread-class.md#resumethread)を呼び出してスレッドを再開することです。

この方法のどちらかを使うと、`CWinThread` オブジェクトの終了理由を判定できます。

## <a name="see-also"></a>関連項目

[C++ と MFC を使用するマルチスレッド](multithreading-with-cpp-and-mfc.md)<br/>
[_endthread、_endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)<br/>
[_beginthread、_beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)<br/>
[ExitThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-exitthread)
