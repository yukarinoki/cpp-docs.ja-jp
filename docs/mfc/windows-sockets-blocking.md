---
description: '詳細については、「Windows Sockets: Block」を参照してください。'
title: Windows ソケット:ブロッキング
ms.date: 11/04/2016
helpviewer_keywords:
- sockets [MFC], blocking mode
- Windows Sockets [MFC], Windows platforms
- Windows Sockets [MFC], blocking mode
- sockets [MFC], behavior on different Windows platforms
- blocking mode sockets
ms.assetid: 10aca9b1-bfba-41a8-9c55-ea8082181e63
ms.openlocfilehash: 21d1a2fb635f3d45e639c950a7ad1748dc3dda74
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197453"
---
# <a name="windows-sockets-blocking"></a>Windows ソケット:ブロッキング

この記事と2つの記事では、Windows ソケットプログラミングにおけるいくつかの問題について説明します。 この記事では、ブロックについて説明します。 その他の問題については、「 [Windows ソケット: バイトの順序付け](../mfc/windows-sockets-byte-ordering.md) 」および [「Windows ソケット: 文字列の変換](../mfc/windows-sockets-converting-strings.md)」で説明されています。

[CAsyncSocket](../mfc/reference/casyncsocket-class.md)クラスを使用する場合、またはクラスを派生させる場合は、これらの問題を自分で管理する必要があります。 またはを使用する場合は、 [MFC でそれらを管理](../mfc/reference/csocket-class.md)します。

## <a name="blocking"></a>ブロッキング

ソケットは、"ブロックモード" または "非ブロッキングモード" になります。 ブロッキング (または同期) モードのソケットの関数は、アクションを完了するまで戻りません。 これは、呼び出しが戻るまで、関数が呼び出されたソケットが何も実行できない (ブロックされている) ため、ブロッキングと呼ばれます。 たとえば、メンバー関数の呼び出しは、 `Receive` 送信元アプリケーションが送信されるのを待機するため、完了までにかなり長い時間がかかることがあります (これは、を使用している場合 `CSocket` 、または with block を使用している場合です `CAsyncSocket` )。 `CAsyncSocket`オブジェクトが非ブロッキングモード (非同期で動作) である場合、呼び出しはすぐに返され、 [GetLastError](../mfc/reference/casyncsocket-class.md#getlasterror)メンバー関数を使用して取得可能な現在のエラーコードは **WSAEWOULDBLOCK** であり、呼び出しがブロックされたことを示します。これは、モードのためすぐに返されないことを示します。 ( `CSocket` **WSAEWOULDBLOCK** は返されません。 クラスは、ブロックを管理します。)

ソケットの動作は、16ビットオペレーティングシステム (windows 3.1 など) よりも32ビットおよび64ビットのオペレーティングシステム (Windows 95 や Windows 98 など) では異なります。 16ビットオペレーティングシステムとは異なり、32ビットおよび64ビットのオペレーティングシステムはプリエンプティブなマルチタスクを使用し、マルチスレッドを提供します。 32ビットおよび64ビットのオペレーティングシステムでは、ソケットを別のワーカースレッドに配置できます。 スレッド内のソケットは、アプリケーション内の他のアクティビティに干渉することなくブロックできます。また、ブロックにコンピューティング時間を費やすこともありません。 マルチスレッドプログラミングの詳細については、「 [マルチスレッド](../parallel/multithreading-support-for-older-code-visual-cpp.md)」を参照してください。

> [!NOTE]
> マルチスレッドアプリケーションでは、のブロックの性質を使用して、 `CSocket` ユーザーインターフェイスの応答性に影響を与えることなく、プログラムの設計を簡略化できます。 メインスレッドでユーザー操作を処理し、 `CSocket` 別のスレッドで処理することで、これらの論理操作を分離できます。 マルチスレッド化されていないアプリケーションでは、これらの2つのアクティビティを組み合わせて1つのスレッドとして処理する必要があります。通常は、を使用して `CAsyncSocket` 、要求時の通信要求を処理したり、 `CSocket::OnMessagePending` 時間のかかる同期アクティビティ中にユーザーの操作を処理するようにオーバーライドしたりすることができます。

この説明の残りの部分は、16ビットオペレーティングシステムを対象とするプログラマ向けです。

通常、を使用している場合は、 `CAsyncSocket` 代わりにブロッキング操作の使用を避け、非同期的に操作する必要があります。 非同期操作では、を呼び出した後に **WSAEWOULDBLOCK** エラーコードを受け取ったポイントから、 `Receive` `OnReceive` もう一度読み取ることができることを通知するためにメンバー関数が呼び出されるまで待機します。 非同期呼び出しは、ソケットの適切なコールバック通知関数 ( [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive)など) を呼び出すことによって行われます。

Windows では、ブロック呼び出しは不適切な方法と見なされます。 既定では、 [CAsyncSocket](../mfc/reference/casyncsocket-class.md) は非同期呼び出しをサポートしており、コールバック通知を使用して自分でブロックを管理する必要があります。 一方、クラスの [CSocket](../mfc/reference/csocket-class.md)は同期です。 Windows メッセージをポンプし、ブロックを管理します。

ブロックの詳細については、「Windows Sockets specification」を参照してください。 "On" 関数の詳細については、「 [Windows ソケット: ソケット通知](../mfc/windows-sockets-socket-notifications.md) 」および「 [Windows ソケット: ソケットクラスからの派生](../mfc/windows-sockets-deriving-from-socket-classes.md)」を参照してください。

詳細については、次を参照してください。

- [Windows ソケット: CAsyncSocket クラスの使用](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows ソケット: アーカイブでのソケットの使用](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows ソケット:背景](../mfc/windows-sockets-background.md)

- [Windows ソケット: ストリームソケット](../mfc/windows-sockets-stream-sockets.md)

- [Windows ソケット: データグラムソケット](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>関連項目

[MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)<br/>
[CAsyncSocket:: OnSend](../mfc/reference/casyncsocket-class.md#onsend)
