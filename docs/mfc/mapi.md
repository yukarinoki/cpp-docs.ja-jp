---
title: MAPI
ms.date: 11/04/2016
helpviewer_keywords:
- messaging [MFC], client applications
- enabling applications for MAPI [MFC]
- MAPI support in MFC
- e-mail [MFC], enabling
- mail [MFC], enabling your application
- MAPI, MFC
- enabling applications for mail [MFC]
ms.assetid: 193449f7-b131-4ab0-9301-8d4f6cd1e7c4
ms.openlocfilehash: 0008a2bc433401f3e048b6f5a92cded88114d08e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625549"
---
# <a name="mapi"></a>MAPI

この記事では、クライアントメッセージアプリケーション開発者向けの Microsoft Messaging Application Programming Interface (MAPI) について説明します。 MFC は、クラスの MAPI のサブセットをサポートしてい `CDocument` ますが、API 全体をカプセル化していません。 詳細については、「 [MFC での MAPI サポート](mapi-support-in-mfc.md)」を参照してください。

MAPI は、メールを有効にし、メールを認識するアプリケーションが、メールメッセージの作成、操作、転送、および保存に使用する一連の機能です。 これにより、アプリケーション開発者はメールメッセージの目的と内容を定義するツールを使用できるようになり、保存されたメールメッセージを柔軟に管理できるようになります。 また、MAPI には、アプリケーション開発者が、基になるメッセージングシステムとは独立して、メール対応アプリケーションとメール対応アプリケーションを作成するために使用できる共通インターフェイスも用意されています。

メッセージングクライアントは、Microsoft Windows Messaging System (WMS) と対話するためのユーザーインターフェイスを提供します。 通常、この相互作用には、メッセージストアやアドレス帳などの MAPI 準拠プロバイダーからのサービスの要求が含まれます。

MAPI の詳細については、Windows SDK の「Win32 Messaging (MAPI) のガイド」の記事を参照してください。

## <a name="in-this-section"></a>このセクションの内容

[MAPI サポート (MFC)](mapi-support-in-mfc.md)

## <a name="see-also"></a>関連項目

[CDocument:: OnFileSendMail](reference/cdocument-class.md#onfilesendmail)<br/>
[CDocument:: OnUpdateFileSendMail](reference/cdocument-class.md#onupdatefilesendmail)<br/>
[COleDocument:: OnFileSendMail](reference/coledocument-class.md#onfilesendmail)
