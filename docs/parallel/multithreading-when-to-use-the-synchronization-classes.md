---
description: '詳細については、「マルチスレッド: MFC 同期クラスを使用する場合」を参照してください。'
title: 'マルチスレッド: MFC 同期クラスを使用する場合'
ms.date: 08/27/2018
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
ms.openlocfilehash: 02776bc61ed702ee81ce0f7373dd442a9fc3d446
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149852"
---
# <a name="multithreading-when-to-use-the-mfc-synchronization-classes"></a>マルチスレッド: MFC 同期クラスを使用する場合

MFC に用意されているマルチスレッドクラスは、同期オブジェクト ([CSyncObject](../mfc/reference/csyncobject-class.md)、 [CSemaphore](../mfc/reference/csemaphore-class.md)、 [CMutex](../mfc/reference/cmutex-class.md)、 [CCriticalSection](../mfc/reference/ccriticalsection-class.md)、および [CEvent](../mfc/reference/cevent-class.md)) と同期アクセスオブジェクト ([CMultiLock](../mfc/reference/cmultilock-class.md) と [CSingleLock](../mfc/reference/csinglelock-class.md)) の2つのカテゴリに分類されます。

同期クラスは、リソースの整合性を確保するためにリソースへのアクセスを制御する必要がある場合に使用されます。 同期アクセスクラスは、これらの制御されたリソースへのアクセスを取得するために使用されます。 このトピックでは、各クラスを使用するタイミングについて説明します。

どの同期クラスを使用するかを決定するには、次の一連の質問に回答してください。

1. アプリケーションは、リソースにアクセスする前に何らかの処理が行われるのを待機する必要があります (たとえば、ファイルに書き込む前に通信ポートからデータを受信する必要があります)。

   「はい」の場合は、を使用 `CEvent` します。

2. 同じアプリケーション内の複数のスレッドが、一度にこのリソースにアクセスできます (たとえば、アプリケーションでは、同じドキュメントのビューを5つまで含むことができます)。

   「はい」の場合は、を使用 `CSemaphore` します。

3. 複数のアプリケーションでこのリソースを使用できますか (たとえば、リソースが DLL 内にある)。

   「はい」の場合は、を使用 `CMutex` します。

   ない場合は、を使用 `CCriticalSection` します。

`CSyncObject` が直接使用されることはありません。 これは、他の4つの同期クラスの基本クラスです。

## <a name="example-1-using-three-synchronization-classes"></a>例 1: 3 つの同期クラスの使用

たとえば、アカウントのリンク リストを保持するアプリケーションの場合を考えます。 このアプリケーションでは 3 つまでのアカウントを個別のウィンドウで調べることができます。ただし、一度に更新できるアカウントは 1 つだけとします。 更新されたデータはネットワークを通じてデータ アーカイブに送られます。

このアプリケーションでは、3 種類の同期クラスをすべて使います。 最大3つのアカウントを一度に調べることができるため、を使用して、 `CSemaphore` 3 つのビューオブジェクトへのアクセスを制限します。 4 番目のアカウントを表示しようとすると、アプリケーションは最初の 3 つのウィンドウのいずれかが閉じるのを待つか、失敗します。 アカウントが更新されると、アプリケーションはを使用して、一度 `CCriticalSection` に1つのアカウントのみが更新されるようにします。 更新が成功すると、 `CEvent` イベントがシグナル状態になるのを待機しているスレッドを解放するシグナルが通知されます。 新しいデータは、このスレッドからデータ アーカイブに送られます。

## <a name="example-2-using-synchronization-access-classes"></a>例 2: 同期アクセスクラスの使用

使用する同期アクセスクラスの選択は、さらに簡単になります。 アプリケーションが1つの制御されたリソースにのみアクセスする場合は、を使用 `CSingleLock` します。 制御された複数のリソースのいずれかにアクセスする必要がある場合は、を使用 `CMultiLock` します。 例1では `CSingleLock` が使用されています。各ケースでは、特定の時間に1つのリソースのみが必要になるためです。

同期クラスの使用方法の詳細については、「 [マルチスレッド: 同期クラスの使用方法](multithreading-how-to-use-the-synchronization-classes.md)」を参照してください。 同期の詳細については、「Windows SDK での [同期](/windows/win32/Sync/synchronization) 」を参照してください。 MFC でのマルチスレッドのサポートの詳細については、「 [C++ と mfc を使用したマルチスレッド](multithreading-with-cpp-and-mfc.md)」を参照してください。

## <a name="see-also"></a>関連項目

[C++ と MFC を使用するマルチスレッド](multithreading-with-cpp-and-mfc.md)
