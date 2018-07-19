---
title: 'マルチ スレッド: 同期クラスを使用する場合 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- threading [MFC], synchronization classes
- resources [C++], multithreading
- synchronization classes [C++]
- synchronization [C++], multithreading
- controlled resource access [C++]
- synchronization access classes [C++]
- threading [C++], synchronization
- multithreading [C++], synchronization classes
ms.assetid: 4914f54e-68ac-438f-93c9-c013455a657e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b05922b826de81b5192b183e1c0afdfcda189f03
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33688259"
---
# <a name="multithreading-when-to-use-the-synchronization-classes"></a>マルチスレッド : 同期クラスの使い分け
MFC で提供されるマルチ スレッドのクラスは 2 つのカテゴリに分類されます同期オブジェクト ([関数](../mfc/reference/csyncobject-class.md)、 [CSemaphore](../mfc/reference/csemaphore-class.md)、 [CMutex](../mfc/reference/cmutex-class.md)、 [ 。CCriticalSection](../mfc/reference/ccriticalsection-class.md)、および[CEvent](../mfc/reference/cevent-class.md)) と同期アクセス オブジェクト ([CMultiLock](../mfc/reference/cmultilock-class.md)と[CSingleLock](../mfc/reference/csinglelock-class.md))。  
  
 同期クラスの使用時に、リソースの整合性を確保するリソースへのアクセスを制御する必要があります。 同期アクセス クラスは、これらの被制御リソースにアクセスするために使用されます。 このトピックでは、各クラスを使用する場合について説明します。  
  
 同期クラスを使用する必要がありますを調べるには、次の一連の質問をしてください。  
  
1.  アプリケーションがリソースにアクセスできる前に発生するものを待機する (たとえば、データ必要がありますから受信する通信ポートをファイルに書き込む前に)?  
  
     使用する場合は、`CEvent`です。  
  
2.  複数のスレッド同じアクセス権をアプリケーション内でこのリソース一度に 1 つ (たとえば、アプリケーションが、最大 5 つのウィンドウのビューの同じドキュメントに許可する) か。  
  
     使用する場合は、`CSemaphore`です。  
  
3.  このリソースを使用して複数のアプリケーション (たとえば、リソースは、DLL) ですか?  
  
     使用する場合は、`CMutex`です。  
  
     ない場合を使用して`CCriticalSection`です。  
  
 **関数**直接は使用されていません。 その他の 4 つの同期クラスの基本クラスです。  
  
## <a name="example-1-using-three-synchronization-classes"></a>例 1: を使用して 3 つの同期クラス  
 たとえば、アカウントのリンク リストを保持するアプリケーションの場合を考えます。 このアプリケーションでは 3 つまでのアカウントを個別のウィンドウで調べることができます。ただし、一度に更新できるアカウントは 1 つだけとします。 更新されたデータはネットワークを通じてデータ アーカイブに送られます。  
  
 このアプリケーションでは、3 種類の同期クラスをすべて使います。 使用して一度に 1 つ調査するを最大 3 つのアカウントでできるように、`CSemaphore`を 3 つのビュー オブジェクトへのアクセスを制限します。 4 番目のアカウントを表示しようとすると、アプリケーションは最初の 3 つのウィンドウのいずれかが閉じるのを待つか、失敗します。 アカウントが更新されると、アプリケーションを使用して`CCriticalSection`一度に 1 つだけのアカウントが更新されるようにします。 更新プログラムが成功、 `CEvent`、シグナル状態になるイベントを待機しているスレッドを解放します。 新しいデータは、このスレッドからデータ アーカイブに送られます。  
  
## <a name="example-2-using-synchronization-access-classes"></a>例 2: 同期アクセス クラスを使用します。  
 同期アクセス クラスを使用して、さらに単純を選択します。 場合は、アプリケーションで 1 つの被制御リソースのみにアクセスするのを使用して`CSingleLock`です。 被制御リソース数のいずれかへのアクセスを必要とする場合を使用して`CMultiLock`です。 例 1 で`CSingleLock`が使用されている特定の時点に各ケースで 1 つのリソースが必要なためです。  
  
 同期クラスの使用方法については、次を参照してください。[マルチ スレッド: 同期クラスを使用する方法](../parallel/multithreading-how-to-use-the-synchronization-classes.md)です。 同期については、次を参照してください。[同期](http://msdn.microsoft.com/library/windows/desktop/ms686353)で、[!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]です。 MFC でマルチ スレッド処理のサポートについては、次を参照してください。 [C++ と MFC を使用するマルチ スレッド](../parallel/multithreading-with-cpp-and-mfc.md)です。  
  
## <a name="see-also"></a>関連項目  
 [C++ と MFC を使用するマルチスレッド](../parallel/multithreading-with-cpp-and-mfc.md)