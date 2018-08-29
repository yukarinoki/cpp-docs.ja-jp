---
title: 'マルチ スレッド: MFC のプログラミングのヒント |Microsoft Docs'
ms.custom: ''
ms.date: 08/27/2018
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
ms.openlocfilehash: 28446576fefe52dfaa99b69ae410a87424e28e3b
ms.sourcegitcommit: f7703076b850c717c33d72fb0755fbb2215c5ddc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "43132039"
---
# <a name="multithreading-mfc-programming-tips"></a>マルチ スレッド: MFC のプログラミングのヒント
マルチ スレッド アプリケーションでは、目的の順序で操作が発生して、複数のスレッドによってアクセスされるすべてのデータが破損していないことを確認して、シングル スレッド アプリケーションより慎重が必要です。 このトピックでは、MFC (Microsoft Foundation Class) ライブラリを使用してマルチスレッド アプリケーションを開発する場合にこのような問題を回避する手法について説明します。  
  
- [複数のスレッドからオブジェクトへのアクセス](#_core_accessing_objects_from_multiple_threads)  
  
- [非 MFC スレッドから MFC オブジェクトへのアクセス](#_core_accessing_mfc_objects_from_non.2d.mfc_threads)  
  
- [Windows ハンドルのマップ](#_core_windows_handle_maps)  
  
- [スレッド間通信](#_core_communicating_between_threads)  
  
##  <a name="_core_accessing_objects_from_multiple_threads"></a> 複数のスレッドからオブジェクトへのアクセス  
 
MFC オブジェクトは、単独でスレッド セーフではできません。 2 つのスレッドはクリティカル セクションなど、MFC 同期クラスや、適切な Win32 の同期オブジェクトを使用しない限り、同じオブジェクトを操作できません。 関連オブジェクトはクリティカル セクションとその他の詳細についてを参照してください[同期](/windows/desktop/Sync/synchronization)Windows SDK に含まれています。  
  
クラス ライブラリは内部的にクリティカル セクションを使って、デバッグ メモリの割り当てなどが使うグローバル データ構造を保護しています。  
  
##  <a name="_core_accessing_mfc_objects_from_non.2d.mfc_threads"></a> 非 MFC スレッドから MFC オブジェクトへのアクセス  
 
使用して以外の方法でスレッドを作成するマルチ スレッド アプリケーションがある場合、 [CWinThread](../mfc/reference/cwinthread-class.md)オブジェクト、そのスレッドから MFC オブジェクトにアクセスすることはできません。 つまり、セカンダリ スレッドから MFC オブジェクトにアクセスする場合は、作成する必要がそのスレッドで説明する方法のいずれかで[マルチ スレッド: ユーザー インターフェイス スレッドの作成](multithreading-creating-user-interface-threads.md)または[マルチ スレッド。ワーカー スレッドを作成する](multithreading-creating-worker-threads.md)します。 ほかの方法では、マルチスレッド アプリケーションの実行に必要な内部変数をクラス ライブラリで初期化できません。  
  
##  <a name="_core_windows_handle_maps"></a> Windows ハンドルのマップ  
 
通常、スレッドは自分自身が作成した MFC オブジェクトしかアクセスできません。 これは、Windows ハンドルの一時マップとパーマネント マップがスレッド ローカル ストレージに保持されており、複数のスレッドから同時にアクセスできないためです。 たとえば、あるワーカー スレッドで計算を行ってから、ドキュメント オブジェクトの `UpdateAllViews`メンバー関数を呼び出して、新しいデータに対するビューの格納先ウィンドウに反映させることはできません。 これも何も起こりません、ためからマップ`CWnd`Hwnd オブジェクトは、プライマリ スレッドに対してローカルです。 つまり、あるスレッドで Windows ハンドルから C++ オブジェクトへのマップが行われるときに、別のスレッドで同じハンドルを別の C++ オブジェクトにマップが行われることもあります。 あるスレッドで行われた変更は、ほかのスレッドには反映されません。  
  
この問題を解決する方法はいくつかあります。 まずは、ワーカー スレッドに C++ オブジェクトではなく、個々 のハンドル (HWND) などを渡すです。 ワーカー スレッドは該当する `FromHandle` メンバー関数を呼び出して、一時マップにオブジェクトを登録します。 呼び出すことによって、スレッドのパーマネント マップにオブジェクトを追加することもできます`Attach`が、オブジェクトはスレッドよりも長く存在が保証する場合にのみこれ行う必要があります。  
  
ワーカー スレッドを実行して、アプリケーションのメイン ウィンドウにこれらのメッセージを投稿は、さまざまなタスクに対応する新しいユーザー定義のメッセージを作成する方法のもう 1 つを使用して`::PostMessage`します。 この通信方法は、2 つの異なるアプリケーション間の対話動作に似ています。ただし、2 つのスレッドが同じアドレス空間を共有する点が異なります。  
  
ハンドル マップの詳細については、次を参照してください。[テクニカル ノート 3:](../mfc/tn003-mapping-of-windows-handles-to-objects.md)します。 スレッド ローカル ストレージの詳細については、次を参照してください。[スレッド ローカル ストレージ](/windows/desktop/ProcThread/thread-local-storage)と[スレッド ローカル ストレージを使用して](/windows/desktop/ProcThread/using-thread-local-storage)Windows SDK に含まれています。  
  
##  <a name="_core_communicating_between_threads"></a> スレッド間通信  
 
MFC には、スレッドからオブジェクトへのアクセスを同期化して、スレッドの安全性を保証するクラスがあります。 これらのクラスの使用方法については、「[マルチ スレッド: 同期クラスの使用方法](multithreading-how-to-use-the-synchronization-classes.md)と[マルチ スレッド: 同期クラスを使用するときに](multithreading-when-to-use-the-synchronization-classes.md)します。 これらのオブジェクトの詳細については、次を参照してください。[同期](/windows/desktop/Sync/synchronization)Windows SDK に含まれています。  
  
## <a name="see-also"></a>関連項目  

[C++ と MFC を使用するマルチスレッド](multithreading-with-cpp-and-mfc.md)