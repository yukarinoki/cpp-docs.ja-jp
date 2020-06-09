---
title: インターネット上の Active テクノロジ
ms.date: 09/12/2018
helpviewer_keywords:
- Internet applications [MFC], Active technology
ms.assetid: 6f782aa1-5c2f-47a2-9e63-ddd0829d5a08
ms.openlocfilehash: 2cd087c99c1ebdcaa8b4a44524e7691984877f20
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625150"
---
# <a name="active-technology-on-the-internet"></a>インターネット上の Active テクノロジ

アクティブなテクノロジは、世界中のインターネット、またはイントラネットと呼ばれる会社の内部ネットワーク用に、魅力的で動的なコンテンツとアプリケーションを開発者が作成できるオープンプラットフォームです。 Microsoft がインターネットプログラミング用に提供する主なテクノロジを次に示します。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX を置き換える最新テクノロジの詳細については、「 [Activex コントロール](activex-controls.md)」を参照してください。

## <a name="activex-controls"></a>ActiveX コントロール

ActiveX コントロール (以前の OLE コントロール) は、Web ページまたは ActiveX コントロールコンテナーであるその他のアプリケーションに挿入できるオブジェクトです。 例としては、ボタン、株価情報、グラフコントロールなどがあります。 詳細については、「[インターネット上の ActiveX コントロール](activex-controls-on-the-internet.md)」を参照してください。

## <a name="internet-data-download-services"></a>インターネットデータダウンロードサービス

データは、一般的なプロトコルである HTTP、FTP、gopher を使用してインターネット経由でダウンロードできます。 MFC WinInet クラスを使用すると、TCP/IP プロトコルと WinSock プロトコルを抽象化することにより、HTTP、FTP、および gopher プロトコルを使用してデータを簡単に転送できます。 MFC 非同期モニカークラスは、ブロックせずにファイルをダウンロードし、大きなオブジェクトを非同期にレンダリングする方法を提供します。 詳細については、「 [Win32 インターネット拡張機能 (WinInet)](win32-internet-extensions-wininet.md)」を参照してください。

## <a name="active-scripts"></a>アクティブなスクリプト

VBScript およびその他のスクリプト言語では、コントロールを接続し、Web ページに対話機能を追加します。 スクリプトは、処理をサーバーからクライアントに移動します。 たとえば、フォームエントリをクライアントで検証した後、サーバーに送信することができます。

## <a name="html-extensions"></a>HTML 拡張機能

オブジェクトタグなどの HTML 拡張機能が、コントロールとスクリプトをサポートするために追加されました。

## <a name="see-also"></a>関連項目

[MFC インターネットプログラミングの基礎](mfc-internet-programming-basics.md)<br/>
[インターネット上の ActiveX コントロール](activex-controls-on-the-internet.md)<br/>
[Win32 インターネット拡張機能 (WinInet)](win32-internet-extensions-wininet.md)
