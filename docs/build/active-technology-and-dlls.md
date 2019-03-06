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
ms.openlocfilehash: 82e18efe66350349c8cbef7f47b7d1fb226674f1
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57420168"
---
# <a name="active-technology-and-dlls"></a>Active テクノロジと DLL

Active テクノロジは、オブジェクトのサーバーを DLL 内部に完全に実装できます。 この種類のサーバーには、インプロセス サーバーは呼び出されます。 MFC は、Active テクノロジは、サーバーをコンテナーのメイン メッセージ ループにフックする方法を提供していないため、主に、ビジュアル編集のすべての機能のプロセスでサーバーを完全にできません。 MFC では、アクセラレータ キーとアイドル状態時の処理を処理するコンテナー アプリケーションのメッセージ ループへのアクセスが必要です。

オートメーション サーバーを作成しているユーザー インターフェイスを持っていない場合は、サーバーをインプロセス サーバーを作成し、DLL に完全に配置できます。

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [オートメーション サーバー](../mfc/automation-servers.md)

## <a name="see-also"></a>関連項目

[Visual C++ の DLL](../build/dlls-in-visual-cpp.md)
