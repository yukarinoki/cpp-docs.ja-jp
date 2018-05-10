---
title: 'マルチ スレッド: プログラミングのヒント |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- multithreading [C++], programming tips
- handle maps [C++]
- access control [C++], multithreading
- objects [C++], multiple threads and
- non-MFC threads [C++]
- threading [MFC], programming tips
- critical sections [C++]
- synchronization [C++], multithreading
- programming [C++], multithreaded
- communications [C++], between threads
- threading [C++], best practices
- troubleshooting [C++], multithreading
- Windows handle maps [C++]
ms.assetid: ad14cc70-c91c-4c24-942f-13a75e58bf8a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b9c4241b9257244de840db1f57c5e7abcb32f206
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="multithreading-programming-tips"></a>マルチスレッド : プログラミングのヒント
マルチスレッド アプリケーションでデータにアクセスするときは、シングルスレッドの場合より慎重に行う必要があります。 マルチスレッド アプリケーションでは、複数のスレッドがそれぞれ個別に同時に実行されるので、アルゴリズムやデータに関して、複数のスレッドで同じデータが使われることを考慮する必要があります。 このトピックでは、MFC (Microsoft Foundation Class) ライブラリを使用してマルチスレッド アプリケーションを開発する場合にこのような問題を回避する手法について説明します。  
  
-   [複数のスレッドからオブジェクトへのアクセス](#_core_accessing_objects_from_multiple_threads)  
  
-   [非 MFC スレッドから MFC オブジェクトにアクセスします。](#_core_accessing_mfc_objects_from_non.2d.mfc_threads)  
  
-   [ウィンドウ ハンドルのマップ](#_core_windows_handle_maps)  
  
-   [スレッド間通信](#_core_communicating_between_threads)  
  
##  <a name="_core_accessing_objects_from_multiple_threads"></a> 複数のスレッドからオブジェクトへのアクセス  
 サイズおよびパフォーマンス上の理由により、MFC オブジェクトのスレッドの安全性は、オブジェクト レベルでは保証されず、クラス レベルでしか保証されません。 つまり、2 つの異なるスレッドで 2 つの異なる `CString` オブジェクトを操作することはできますが、2 つの異なるスレッドで同じ `CString` オブジェクトを操作することはできません。 複数のスレッドで 1 つのオブジェクトを操作する必要があるときは、Win32 のクリティカル セクションなどの同期機構を使ってアクセスを保護します。 詳細については、クリティカル セクションなどの関連オブジェクトを参照してください。[同期](http://msdn.microsoft.com/library/windows/desktop/ms686353)で、[!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]です。  
  
 クラス ライブラリは内部的にクリティカル セクションを使って、デバッグ メモリの割り当てなどが使うグローバル データ構造を保護しています。  
  
##  <a name="_core_accessing_mfc_objects_from_non.2d.mfc_threads"></a> 非 MFC スレッドから MFC オブジェクトにアクセスします。  
 使用する以外の方法でスレッドを作成するマルチ スレッド アプリケーションがある場合、 [CWinThread](../mfc/reference/cwinthread-class.md)オブジェクト、そのスレッドから MFC オブジェクトにアクセスすることはできません。 つまり、セカンダリ スレッドから MFC オブジェクトにアクセスする場合は、作成する必要がそのスレッドで説明する方法のいずれかの[マルチ スレッド: ユーザー インターフェイス スレッドの生成](../parallel/multithreading-creating-user-interface-threads.md)または[マルチ スレッド。ワーカー スレッドの生成](../parallel/multithreading-creating-worker-threads.md)です。 ほかの方法では、マルチスレッド アプリケーションの実行に必要な内部変数をクラス ライブラリで初期化できません。  
  
##  <a name="_core_windows_handle_maps"></a> ウィンドウ ハンドルのマップ  
 通常、スレッドは自分自身が作成した MFC オブジェクトしかアクセスできません。 これは、Windows ハンドルの一時マップとパーマネント マップがスレッド ローカル ストレージに保持されており、複数のスレッドから同時にアクセスできないためです。 たとえば、あるワーカー スレッドで計算を行ってから、ドキュメント オブジェクトの `UpdateAllViews`メンバー関数を呼び出して、新しいデータに対するビューの格納先ウィンドウに反映させることはできません。 `CWnd` オブジェクトから `HWND` へのマップはプライマリ スレッドに固有であるからです。 つまり、あるスレッドで Windows ハンドルから C++ オブジェクトへのマップが行われるときに、別のスレッドで同じハンドルを別の C++ オブジェクトにマップが行われることもあります。 あるスレッドで行われた変更は、ほかのスレッドには反映されません。  
  
 この問題を解決する方法はいくつかあります。 第 1 の方法は、ワーカー スレッドに C++ オブジェクトを渡さずに `HWND` などのハンドルを個別に渡す方法です。 ワーカー スレッドは該当する `FromHandle` メンバー関数を呼び出して、一時マップにオブジェクトを登録します。 呼び出してスレッドのパーマネント マップにオブジェクトを追加することもでした**アタッチ**、これをする場合にのみ、オブジェクトの存在は、スレッドよりも長くすることが保証されますが、します。  
  
 別の方法は、ワーカー スレッドが実行され、アプリケーションのメイン ウィンドウにこれらのメッセージを投稿は、さまざまなタスクに対応する新しいユーザー定義のメッセージを作成するを使用して **:: PostMessage**です。 この通信方法は、2 つの異なるアプリケーション間の対話動作に似ています。ただし、2 つのスレッドが同じアドレス空間を共有する点が異なります。  
  
 ハンドル マップの詳細については、次を参照してください。[テクニカル ノート 3:](../mfc/tn003-mapping-of-windows-handles-to-objects.md)です。 スレッド ローカル ストレージの詳細については、次を参照してください。[スレッド ローカル ストレージ](http://msdn.microsoft.com/library/windows/desktop/ms686749)と[スレッド ローカル ストレージを使用して](http://msdn.microsoft.com/library/windows/desktop/ms686991)で、[!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]です。  
  
##  <a name="_core_communicating_between_threads"></a> スレッド間通信  
 MFC には、スレッドからオブジェクトへのアクセスを同期化して、スレッドの安全性を保証するクラスがあります。 これらのクラスの使用方法については、「[マルチ スレッド: 同期クラスを使用する方法](../parallel/multithreading-how-to-use-the-synchronization-classes.md)と[マルチ スレッド: 同期クラスを使用するときに](../parallel/multithreading-when-to-use-the-synchronization-classes.md)です。 これらのオブジェクトの詳細については、次を参照してください。[同期](http://msdn.microsoft.com/library/windows/desktop/ms686353)で、[!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [C++ と MFC を使用するマルチスレッド](../parallel/multithreading-with-cpp-and-mfc.md)