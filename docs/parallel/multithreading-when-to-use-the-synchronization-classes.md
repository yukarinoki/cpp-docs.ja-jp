---
title: 'マルチ スレッド: MFC 同期クラスを使用する場合 |Microsoft Docs'
ms.custom: ''
ms.date: 08/27/2018
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
ms.openlocfilehash: 018623e9e6a093c4f86b8768e0fd5329f4ea3282
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443775"
---
# <a name="multithreading-when-to-use-the-mfc-synchronization-classes"></a>マルチ スレッド: MFC 同期クラスを使用する場合

MFC で提供されるマルチ スレッドのクラスが 2 つのカテゴリに分類されます同期オブジェクト ([CSyncObject](../mfc/reference/csyncobject-class.md)、 [CSemaphore](../mfc/reference/csemaphore-class.md)、 [CMutex](../mfc/reference/cmutex-class.md)、 [ 。CCriticalSection](../mfc/reference/ccriticalsection-class.md)、および[CEvent](../mfc/reference/cevent-class.md)) と同期アクセス オブジェクト ([CMultiLock](../mfc/reference/cmultilock-class.md)と[CSingleLock](../mfc/reference/csinglelock-class.md))。

同期クラスの使用時に、リソースの整合性を確保するリソースへのアクセスを制御する必要があります。 同期アクセス クラスは、これらの制御されたリソースへのアクセスに使用されます。 このトピックでは、各クラスを使用する場合について説明します。

同期クラスを使用する必要がありますを確認するのには、次の一連の質問を確認してください。

1. アプリケーションがリソースにアクセスできる前に発生するを待機するには (たとえば、データがから受け取る必要が通信ポートあるをファイルに書き込む前に) でしょうか。

     場合はそれを使用して、`CEvent`します。

2. できます 1 つ以上のスレッド内、同じアプリケーションのアクセスでこのリソース一度に 1 つ (たとえば、アプリケーションが最大 5 つのウィンドウのビューには、同じドキュメントを許可する) か?

     場合はそれを使用して、`CSemaphore`します。

3. このリソースを使用して複数のアプリケーション (リソースは、DLL 内など) ですか?

     場合はそれを使用して、`CMutex`します。

     ない場合を使用して、`CCriticalSection`します。

`CSyncObject` 直接使用されません。 その他の 4 つの同期クラスの基本クラスです。

## <a name="example-1-using-three-synchronization-classes"></a>例 1: 次の 3 つの同期クラスを使用します。

たとえば、アカウントのリンク リストを保持するアプリケーションの場合を考えます。 このアプリケーションでは 3 つまでのアカウントを個別のウィンドウで調べることができます。ただし、一度に更新できるアカウントは 1 つだけとします。 更新されたデータはネットワークを通じてデータ アーカイブに送られます。

このアプリケーションでは、3 種類の同期クラスをすべて使います。 使用して最大 3 つのアカウントで同時に調査するため、`CSemaphore`を 3 つのビュー オブジェクトへのアクセスを制限します。 4 番目のアカウントを表示しようとすると、アプリケーションは最初の 3 つのウィンドウのいずれかが閉じるのを待つか、失敗します。 アカウントを更新すると、アプリケーションを使用して`CCriticalSection`を一度に 1 つだけのアカウントが更新されるようにします。 更新プログラムの成功、 `CEvent`、シグナル状態になるイベントの待機スレッドを解放します。 新しいデータは、このスレッドからデータ アーカイブに送られます。

## <a name="example-2-using-synchronization-access-classes"></a>例 2: 同期アクセス クラスを使用します。

同期アクセス クラスを使用して、さらに簡単かを選択します。 場合は、アプリケーションは、1 つの被制御リソースのみへのアクセスを使用して、`CSingleLock`します。 被制御リソース数のいずれかへのアクセスを必要がある場合を使用して、`CMultiLock`します。 例 1 で`CSingleLock`使用された、特定の時点に各ケースの 1 つだけのリソースが必要なためです。

同期クラスの使用方法については、次を参照してください。[マルチ スレッド: 同期クラスの使用方法](multithreading-how-to-use-the-synchronization-classes.md)します。 同期の詳細については、次を参照してください。[同期](/windows/desktop/Sync/synchronization)Windows SDK に含まれています。 MFC でマルチ スレッドのサポートについては、次を参照してください。 [C++ と MFC を使用するマルチ スレッド](multithreading-with-cpp-and-mfc.md)します。

## <a name="see-also"></a>関連項目

[C++ と MFC を使用するマルチスレッド](multithreading-with-cpp-and-mfc.md)