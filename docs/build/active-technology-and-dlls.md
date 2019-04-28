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
ms.openlocfilehash: 9633d60520a2a634ffe78d0fb9d48f6dd2ca7333
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62195553"
---
# <a name="active-technology-and-dlls"></a>Active テクノロジと DLL

Active テクノロジは、オブジェクトのサーバーを DLL 内部に完全に実装できます。 この種類のサーバーには、インプロセス サーバーは呼び出されます。 MFC は、Active テクノロジは、サーバーをコンテナーのメイン メッセージ ループにフックする方法を提供していないため、主に、ビジュアル編集のすべての機能のプロセスでサーバーを完全にできません。 MFC では、アクセラレータ キーとアイドル状態時の処理を処理するコンテナー アプリケーションのメッセージ ループへのアクセスが必要です。

オートメーション サーバーを作成しているユーザー インターフェイスを持っていない場合は、サーバーをインプロセス サーバーを作成し、DLL に完全に配置できます。

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [オートメーション サーバー](../mfc/automation-servers.md)

## <a name="see-also"></a>関連項目

[Visual C++ の DLL](dlls-in-visual-cpp.md)
