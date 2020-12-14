---
description: 詳細については、「プロジェクトビルドエラー PRJ0050」を参照してください。
title: プロジェクト ビルド エラー PRJ0050
ms.date: 11/04/2016
f1_keywords:
- PRJ0050
helpviewer_keywords:
- PRJ0050
ms.assetid: ceef3b37-0acf-4abd-ac62-aa830b4fa145
ms.openlocfilehash: 07a4df24f48a61e29214431840649566716bbac3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240807"
---
# <a name="project-build-error-prj0050"></a>プロジェクト ビルド エラー PRJ0050

出力を登録できませんでした。 レジストリを変更するための適切なアクセス許可があることを確認してください。

Visual C++ ビルドシステムは、ビルド (dll または .exe) の出力を登録できませんでした。 レジストリを変更するには、管理者としてログオンする必要があります。

.Dll をビルドしている場合は、regsvr32.exe を使用して .dll を手動で登録することができます。これにより、ビルドが失敗した理由に関する情報が表示されます。

.Dll をビルドしていない場合は、エラーの原因となったコマンドのビルドログを確認します。
