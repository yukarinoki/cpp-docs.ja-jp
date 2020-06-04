---
title: プロジェクト ビルドの警告 PRJ0041
ms.date: 11/04/2016
f1_keywords:
- PRJ0041
helpviewer_keywords:
- PRJ0041
ms.assetid: dc9f4cf9-6bd5-4222-89e8-7802a59bb96b
ms.openlocfilehash: bb6469b1daf193223a9b3361cc3e4bfb96d0c751
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80191934"
---
# <a name="project-build-warning-prj0041"></a>プロジェクト ビルドの警告 PRJ0041

ファイル ' file ' の依存関係 ' dependency ' が見つかりません。 プロジェクトは引き続きビルドされる場合がありますが、このファイルが見つかるまでは引き続き期限切れになる可能性があります。

たとえば、ファイル (リソースファイルまたは .idl/odl ファイル) に、プロジェクトシステムが解決できない include ステートメントが含まれています。

プロジェクトシステムがプリプロセッサステートメント (#if など) を処理しないため、実際には、問題のあるステートメントがビルドに含まれないことがあります。

この警告を解決するには、.rc ファイル内の不要なコードをすべて削除するか、適切な名前のプレースホルダーファイルを追加します。
