---
title: 'マルチ スレッド: プログラミングのヒント |Microsoft Docs'
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
ms.openlocfilehash: 2ad830117323aef807fcebc1ef61b4dfb1900bd9
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42591312"
---
# <a name="multithreading-programming-tips"></a>マルチスレッド : プログラミングのヒント
マルチスレッド アプリケーションでデータにアクセスするときは、シングルスレッドの場合より慎重に行う必要があります。 マルチスレッド アプリケーションでは、複数のスレッドがそれぞれ個別に同時に実行されるので、アルゴリズムやデータに関して、複数のスレッドで同じデータが使われることを考慮する必要があります。 このトピックでは、MFC (Microsoft Foundation Class) ライブラリを使用してマルチスレッド アプリケーションを開発する場合にこのような問題を回避する手法について説明します。  
  
- [複数のスレッドからオブジェクトへのアクセス](#_core_accessing_objects_from_multiple_threads)  
  
- [非 MFC スレッドから MFC オブジェクトへのアクセス](#_core_accessing_mfc_objects_from_non.2d.mfc_threads)  
  
- [Windows ハンドルのマップ](#_core_windows_handle_maps)  
  
- [スレッド間通信](#_core_communicating_between_threads)  
  
##  <a name="_core_accessing_objects_from_multiple_threads"></a> 複数のスレッドからオブジェクトへのアクセス  
 
サイズおよびパフォーマンス上の理由により、MFC オブジェクトのスレッドの安全性は、オブジェクト レベルでは保証されず、クラス レベルでしか保証されません。 つまり、2 つの異なるスレッドで 2 つの異なる `CString` オブジェクトを操作することはできますが、2 つの異なるスレッドで同じ `CString` オブジェクトを操作することはできません。 複数のスレッドで 1 つのオブジェクトを操作する必要があるときは、Win32 のクリティカル セクションなどの同期機構を使ってアクセスを保護します。 関連オブジェクトはクリティカル セクションとその他の詳細についてを参照してください[同期](http://msdn.microsoft.com/library/windows/desktop/ms686353)Windows SDK に含まれています。  
  
クラス ライブラリは内部的にクリティカル セクションを使って、デバッグ メモリの割り当てなどが使うグローバル データ構造を保護しています。  
  
##  <a name="_core_accessing_mfc_objects_from_non.2d.mfc_threads"></a> 非 MFC スレッドから MFC オブジェクトへのアクセス  
 
使用して以外の方法でスレッドを作成するマルチ スレッド アプリケーションがある場合、 [CWinThread](../mfc/reference/cwinthread-class.md)オブジェクト、そのスレッドから MFC オブジェクトにアクセスすることはできません。 つまり、セカンダリ スレッドから MFC オブジェクトにアクセスする場合は、作成する必要がそのスレッドで説明する方法のいずれかで[マルチ スレッド: ユーザー インターフェイス スレッドの作成](../parallel/multithreading-creating-user-interface-threads.md)または[マルチ スレッド。ワーカー スレッドを作成する](../parallel/multithreading-creating-worker-threads.md)します。 ほかの方法では、マルチスレッド アプリケーションの実行に必要な内部変数をクラス ライブラリで初期化できません。  
  
##  <a name="_core_windows_handle_maps"></a> Windows ハンドルのマップ  
 
通常、スレッドは自分自身が作成した MFC オブジェクトしかアクセスできません。 これは、Windows ハンドルの一時マップとパーマネント マップがスレッド ローカル ストレージに保持されており、複数のスレッドから同時にアクセスできないためです。 たとえば、あるワーカー スレッドで計算を行ってから、ドキュメント オブジェクトの `UpdateAllViews`メンバー関数を呼び出して、新しいデータに対するビューの格納先ウィンドウに反映させることはできません。 これも何も起こりません、ためからマップ`CWnd`Hwnd オブジェクトは、プライマリ スレッドに対してローカルです。 つまり、あるスレッドで Windows ハンドルから C++ オブジェクトへのマップが行われるときに、別のスレッドで同じハンドルを別の C++ オブジェクトにマップが行われることもあります。 あるスレッドで行われた変更は、ほかのスレッドには反映されません。  
  
この問題を解決する方法はいくつかあります。 まずは、ワーカー スレッドに C++ オブジェクトではなく、個々 のハンドル (HWND) などを渡すです。 ワーカー スレッドは該当する `FromHandle` メンバー関数を呼び出して、一時マップにオブジェクトを登録します。 呼び出すことによって、スレッドのパーマネント マップにオブジェクトを追加することもできます`Attach`が、オブジェクトはスレッドよりも長く存在が保証する場合にのみこれ行う必要があります。  
  
ワーカー スレッドを実行して、アプリケーションのメイン ウィンドウにこれらのメッセージを投稿は、さまざまなタスクに対応する新しいユーザー定義のメッセージを作成する方法のもう 1 つを使用して`::PostMessage`します。 この通信方法は、2 つの異なるアプリケーション間の対話動作に似ています。ただし、2 つのスレッドが同じアドレス空間を共有する点が異なります。  
  
ハンドル マップの詳細については、次を参照してください。[テクニカル ノート 3:](../mfc/tn003-mapping-of-windows-handles-to-objects.md)します。 スレッド ローカル ストレージの詳細については、次を参照してください。[スレッド ローカル ストレージ](http://msdn.microsoft.com/library/windows/desktop/ms686749)と[スレッド ローカル ストレージを使用して](http://msdn.microsoft.com/library/windows/desktop/ms686991)Windows SDK に含まれています。  
  
##  <a name="_core_communicating_between_threads"></a> スレッド間通信  
 
MFC には、スレッドからオブジェクトへのアクセスを同期化して、スレッドの安全性を保証するクラスがあります。 これらのクラスの使用方法については、「[マルチ スレッド: 同期クラスの使用方法](../parallel/multithreading-how-to-use-the-synchronization-classes.md)と[マルチ スレッド: 同期クラスを使用するときに](../parallel/multithreading-when-to-use-the-synchronization-classes.md)します。 これらのオブジェクトの詳細については、次を参照してください。[同期](http://msdn.microsoft.com/library/windows/desktop/ms686353)Windows SDK に含まれています。  
  
## <a name="see-also"></a>関連項目  

[C++ と MFC を使用するマルチスレッド](../parallel/multithreading-with-cpp-and-mfc.md)