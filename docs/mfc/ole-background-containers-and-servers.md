---
description: '詳細については、「OLE バックグラウンド: コンテナーとサーバー」を参照してください。'
title: 'OLE 概要 : コンテナーとサーバー'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE full-server applications [MFC]
- server applications [MFC], communication with containers
- full-server [MFC]
- server applications [MFC], requirements
- server applications [MFC], defined
- OLE server applications [MFC], about server applications
- server applications [MFC], full-server vs. mini-server
- OLE server applications [MFC], mini-server applications
- OLE containers [MFC], container applications
- containers [MFC], OLE container applications
- server applications [MFC]
ms.assetid: dafbb31d-096c-4654-b774-12900d832919
ms.openlocfilehash: 3ea578ce14165b16e84520b22bc545fc5d2a8882
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254777"
---
# <a name="ole-background-containers-and-servers"></a>OLE 概要 : コンテナーとサーバー

コンテナーアプリケーションは、埋め込みまたはリンクされた項目を独自のドキュメントに組み込むことができるアプリケーションです。 コンテナーアプリケーションによって管理されるドキュメントでは、アプリケーション自体によって作成されたデータだけでなく、OLE ドキュメントコンポーネントを格納して表示できる必要があります。 コンテナーアプリケーションでは、必要に応じてサーバーアプリケーションをアクティブ化することで、ユーザーが新しい項目を挿入したり、既存の項目を編集したりできるようにする必要もあります。 コンテナーアプリケーションのユーザーインターフェイスの要件については、「 [コンテナー: User-Interface の問題](containers-user-interface-issues.md)」に記載されています。

サーバーアプリケーションまたはコンポーネントアプリケーションは、コンテナーアプリケーションで使用する OLE ドキュメントコンポーネントを作成できるアプリケーションです。 通常、サーバーアプリケーションは、クリップボードにデータをドラッグアンドドロップまたはコピーすることをサポートしているので、コンテナーアプリケーションはデータを埋め込みまたはリンクされたアイテムとして挿入できます。 アプリケーションには、コンテナーとサーバーの両方を指定できます。

ほとんどのサーバーは、スタンドアロンアプリケーションまたはフルサーバーです。スタンドアロンアプリケーションとして実行するか、コンテナーアプリケーションで起動できます。 ミニサーバーは、コンテナーによってのみ起動できる特殊な種類のサーバーアプリケーションです。 スタンドアロンアプリケーションとして実行することはできません。 ミニサーバーの例としては、Microsoft Draw および Microsoft Graph サーバーが挙げられます。

コンテナーとサーバーは直接通信しません。 代わりに、OLE システムのダイナミックリンクライブラリ (DLL) を介して通信します。 これらの Dll には、コンテナーとサーバーが呼び出す関数が用意されています。また、コンテナーとサーバーは、Dll が呼び出すコールバック関数を提供します。

この通信方法を使用すると、コンテナーはサーバーアプリケーションの実装の詳細を知る必要がありません。 これにより、コンテナーは、使用できるサーバーの種類を定義することなく、任意のサーバーによって作成された項目を受け入れることができます。 その結果、コンテナーアプリケーションのユーザーは、将来のアプリケーションとデータ形式を利用できます。 これらの新しいアプリケーションが OLE コンポーネントである場合、複合ドキュメントには、それらのアプリケーションによって作成されたアイテムを組み込むことができます。

## <a name="see-also"></a>関連項目

[OLE の背景](ole-background.md)<br/>
[OLE の背景知識: MFC の実装](ole-background-mfc-implementation.md)<br/>
[Containers](containers.md)<br/>
[サーバー](servers.md)<br/>
[コンテナー: クライアントアイテム](containers-client-items.md)<br/>
[サーバー: サーバー項目](servers-server-items.md)
