---
title: Active テクノロジと DLL
ms.date: 11/04/2016
helpviewer_keywords:
- in-process server DLLs
- Automation [C++], DLLs
- DLLs [C++], Active Technology
- Active technology [C++]
- MFC DLLs [C++], Active Technology
ms.assetid: 3ed27f8d-164a-4562-ad61-9f2333404cc7
ms.openlocfilehash: 270c64df9af792a73acf1ad408aca02e7fadc30f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50535812"
---
# <a name="active-technology-and-dlls"></a>Active テクノロジと DLL

Active テクノロジは、オブジェクトのサーバーを DLL 内部に完全に実装できます。 この種類のサーバーには、インプロセス サーバーは呼び出されます。 MFC は、Active テクノロジは、サーバーをコンテナーのメイン メッセージ ループにフックする方法を提供していないため、主に、ビジュアル編集のすべての機能のプロセスでサーバーを完全にできません。 MFC では、アクセラレータ キーとアイドル状態時の処理を処理するコンテナー アプリケーションのメッセージ ループへのアクセスが必要です。

オートメーション サーバーを作成しているユーザー インターフェイスを持っていない場合は、サーバーをインプロセス サーバーを作成し、DLL に完全に配置できます。

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [オートメーション サーバー](../mfc/automation-servers.md)

## <a name="see-also"></a>関連項目

[Visual C++ の DLL](../build/dlls-in-visual-cpp.md)