---
description: 詳細については、「アプリケーションとスレッドのサポートクラス」を参照してください。
title: アプリケーションおよびスレッド サポート クラス
ms.date: 11/04/2016
f1_keywords:
- vc.classes.support
helpviewer_keywords:
- application objects [MFC], thread support classes
- lock classes [MFC]
- thread support classes [MFC]
- threading [MFC]
- synchronization classes [MFC], multithreading
- application support classes [MFC]
ms.assetid: 3c1d14fd-c35c-48f1-86ce-1e0f9a32c36d
ms.openlocfilehash: 89ab6e324a777c272dcbcfabc746c03cb6731589
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176744"
---
# <a name="application-and-thread-support-classes"></a>アプリケーションおよびスレッド サポート クラス

各アプリケーションには、アプリケーションオブジェクトが1つだけあります。このオブジェクトは、実行中のプログラム内の他のオブジェクトを調整し、から派生し `CWinApp` ます。

MFC (Microsoft Foundation Class) ライブラリでは、アプリケーション内での複数のスレッドの実行がサポートされています。 すべてのアプリケーションには、少なくとも1つのスレッドが必要です。オブジェクトによって使用されるスレッド `CWinApp` は、このプライマリスレッドです。

`CWinThread` オペレーティングシステムのスレッド処理機能の一部をカプセル化します。 複数のスレッドを簡単に使用できるようにするために、MFC には、Win32 同期オブジェクトに C++ インターフェイスを提供する同期オブジェクトクラスも用意されています。

## <a name="application-and-thread-classes"></a>アプリケーションクラスとスレッドクラス

[CWinApp](reference/cwinapp-class.md)<br/>
アプリケーションを初期化し、実行し、終了するコードをカプセル化します。 このクラスからアプリケーションオブジェクトを派生させます。

[CWinThread](reference/cwinthread-class.md)<br/>
すべてのスレッドの基本クラス。 を直接使用するか、 `CWinThread` スレッドがユーザーインターフェイス関数を実行する場合はからクラスを派生させます。 `CWinApp` は、`CWinThread` から派生しています。

## <a name="synchronization-object-classes"></a>同期オブジェクトクラス

[CSyncObject](reference/csyncobject-class.md)<br/>
同期オブジェクトクラスの基本クラスです。

[CCriticalSection](reference/ccriticalsection-class.md)<br/>
1つのプロセス内で1つのスレッドだけがオブジェクトにアクセスできるようにする同期クラス。

[CSemaphore](reference/csemaphore-class.md)<br/>
1つのオブジェクトと指定した最大数の同時アクセスを許可する同期クラス。

[CMutex](reference/cmutex-class.md)<br/>
任意の数のプロセス内の1つのスレッドだけがオブジェクトにアクセスできるようにする同期クラス。

[CEvent](reference/cevent-class.md)<br/>
イベントが発生したときにアプリケーションに通知する同期クラス。

[CSingleLock](reference/csinglelock-class.md)<br/>
スレッドセーフなクラスのメンバー関数で、1つの同期オブジェクトをロックするために使用されます。

[CMultiLock](reference/cmultilock-class.md)<br/>
同期オブジェクトの配列から1つ以上の同期オブジェクトをロックするために、スレッドセーフクラスのメンバー関数で使用されます。

## <a name="related-classes"></a>関連クラス

[CCommandLineInfo](reference/ccommandlineinfo-class.md)<br/>
プログラムが起動されたコマンドラインを解析します。

[CWaitCursor](reference/cwaitcursor-class.md)<br/>
画面に待機カーソルを置きます。 時間のかかる操作中に使用されます。

[CDockState](reference/cdockstate-class.md)<br/>
コントロールバーのドッキング状態データの永続ストレージを処理します。

[CRecentFileList](reference/crecentfilelist-class.md)<br/>
最近使用した (MRU) ファイルの一覧を保持します。

## <a name="see-also"></a>関連項目

[クラスの概要](class-library-overview.md)
