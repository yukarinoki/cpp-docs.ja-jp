---
title: 'マルチ スレッド: MFC 同期クラスを使用する方法 |Microsoft Docs'
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], multithreading
- threading [MFC], synchronization classes
- resources [C++], multithreading
- thread-safe classes [C++]
- synchronization classes [C++]
- synchronization [C++], multithreading
- threading [MFC], thread-safe class design
- threading [C++], synchronization
- multithreading [C++], synchronization classes
- threading [C++], thread-safe class design
ms.assetid: f266d4c6-0454-4bda-9758-26157ef74cc5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ca2603c2ba96cbf0df04f56d2334bd6e65110ac6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46447974"
---
# <a name="multithreading-how-to-use-the-mfc-synchronization-classes"></a>MFC 同期クラスを使用する方法をマルチ スレッド。

リソースにアクセスする複数のスレッドの同期は、マルチスレッド アプリケーションを書くときに共通の問題です。 複数のスレッドから同じデータに同時にアクセスすると、予測できない結果になることがあります。 たとえば、あるスレッドで構造体の内容を更新しているときに、別のスレッドが同じ構造体の内容を読み取るということが考えられます。 この場合、後者のスレッドが実際に読み取った内容が、古いデータになるか更新後のデータになるかはわかりません。古いデータと更新データが混在することも考えられます。 MFC (Microsoft Foundation Class) の同期クラスと同期アクセス クラスを使うと、この問題を解決できます。 このトピックでは、これらのクラスを使用して、一般的なマルチスレッド アプリケーションでスレッド セーフなクラスを作成する方法を説明します。

一般的なマルチスレッド アプリケーションには、スレッド間の共有リソースを表すクラスがあります。 スレッドセーフなクラスをデザインすると、同期関数を呼び出す必要がありません。 リソースへのアクセスをすべてクラス内部で処理するので、プログラマはクラスの破損などを気にせずに、クラスを最大限に活用する方法だけを考えることができます。 スレッド セーフなクラスを作成するには、同期クラスをリソース クラス内にマージすることが効果的な方法です。 同期クラスの共有クラスへのマージは簡単に行うことができます。

たとえば、アカウントのリンク リストを保持するアプリケーションの場合を考えます。 このアプリケーションでは 3 つまでのアカウントを個別のウィンドウで調べることができます。ただし、一度に更新できるアカウントは 1 つだけとします。 更新されたデータはネットワークを通じてデータ アーカイブに送られます。

このアプリケーションでは、3 種類の同期クラスをすべて使います。 使用して最大 3 つのアカウントで同時に調査するため、 [CSemaphore](../mfc/reference/csemaphore-class.md)を 3 つのビュー オブジェクトへのアクセスを制限します。 4 番目のアカウントを表示しようとすると、アプリケーションは最初の 3 つのウィンドウのいずれかが閉じるのを待つか、失敗します。 アカウントを更新すると、アプリケーションを使用して[CCriticalSection](../mfc/reference/ccriticalsection-class.md)を一度に 1 つだけのアカウントが更新されるようにします。 更新プログラムの成功、 [CEvent](../mfc/reference/cevent-class.md)、シグナル状態になるイベントの待機スレッドを解放します。 新しいデータは、このスレッドからデータ アーカイブに送られます。

##  <a name="_mfc_designing_a_thread.2d.safe_class"></a> スレッド セーフなクラスの設計

スレッドセーフなクラスにするには、まず、該当する同期クラスをデータ メンバーとして共有クラスに追加します。 アカウント管理の前の例で、`CSemaphore`データ メンバーは、ビュー クラスに追加、`CCriticalSection`データ メンバーは、リンク リスト クラスに追加し、`CEvent`データ メンバーは、データ記憶域クラスに追加します。

次に、クラス内のデータを変更する、または被制御リソースにアクセスするすべてのメンバー関数への同期呼び出しを追加します。 各関数で、いずれかを作成する必要があります、 [CSingleLock](../mfc/reference/csinglelock-class.md)または[CMultiLock](../mfc/reference/cmultilock-class.md)オブジェクトし、そのオブジェクトの`Lock`関数。 ロック オブジェクトがスコープ外に出て破棄されると、このオブジェクトのデストラクターによって `Unlock` が呼び出され、リソースが解放されます。 必要に応じて、`Unlock` を直接呼び出すこともできます。

このようにスレッド セーフなクラスをデザインすると、非スレッド セーフなクラスと同じように、マルチスレッド アプリケーションで簡単に使用できるだけでなく、安全性も保証されます。 同期オブジェクトと同期アクセス オブジェクトをリソースのクラスにカプセル化すると、同期コードを使わずに、スレッドを安全に使用できます。

次のコード例では、共有リソース クラスで宣言されたデータ メンバー `m_CritSection` (`CCriticalSection` 型) と `CSingleLock` オブジェクトを使って、この方法を示します。 `CWinThread` から派生する共有リソースの同期は、`CSingleLock` オブジェクトのアドレスを使って `m_CritSection` オブジェクトを作成することによって行います。 まず、リソースのロックを行い、ロックを取得すると、共有オブジェクト側の作業は完了です。 作業が完了すると、`Unlock` 呼び出しによってリソースのロックが解除されます。

```
CSingleLock singleLock(&m_CritSection);
singleLock.Lock();
// resource locked
//.usage of shared resource...

singleLock.Unlock();
```

> [!NOTE]
> `CCriticalSection` には、その他の MFC 同期クラスと異なり、期限付きのロック要求オプションがありません。 スレッドが解放されるまでの待機時間は無限です。

この手法の欠点は、同期オブジェクトを追加しない場合と比べて、クラスの動作が少し遅くなることです。 また、同期オブジェクトを複数のスレッドで削除した場合は、マージが成功するとは限りません。 このような場合は、同期オブジェクトを別個に管理します。

さまざまな状況で使用する同期クラスを決定する方法の詳細については、次を参照してください。[マルチ スレッド: 同期クラスを使用するときに](multithreading-when-to-use-the-synchronization-classes.md)します。 同期の詳細については、次を参照してください。[同期](/windows/desktop/Sync/synchronization)Windows SDK に含まれています。 MFC でマルチ スレッドのサポートの詳細については、次を参照してください。 [C++ と MFC を使用するマルチ スレッド](multithreading-with-cpp-and-mfc.md)します。

## <a name="see-also"></a>関連項目

[C++ と MFC を使用するマルチスレッド](multithreading-with-cpp-and-mfc.md)