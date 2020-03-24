---
title: プロジェクト ビルド エラー PRJ0050
ms.date: 11/04/2016
f1_keywords:
- PRJ0050
helpviewer_keywords:
- PRJ0050
ms.assetid: ceef3b37-0acf-4abd-ac62-aa830b4fa145
ms.openlocfilehash: 56e092b5f7c33ad9543951621b2a9d8f6992331f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80191991"
---
# <a name="project-build-error-prj0050"></a>プロジェクト ビルド エラー PRJ0050

出力を登録できませんでした。 レジストリを変更するための適切なアクセス許可があることを確認してください。

Visual C++ビルドシステムは、ビルド (dll または .exe) の出力を登録できませんでした。 レジストリを変更するには、管理者としてログオンする必要があります。

.Dll をビルドしている場合は、regsvr32 を使用して .dll を手動で登録することができます。これにより、ビルドが失敗した理由に関する情報が表示されます。

.Dll をビルドしていない場合は、エラーの原因となったコマンドのビルドログを確認します。
