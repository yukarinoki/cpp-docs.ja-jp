---
description: 詳細については、「プロジェクトビルドの警告 PRJ0041」を参照してください。
title: プロジェクト ビルドの警告 PRJ0041
ms.date: 11/04/2016
f1_keywords:
- PRJ0041
helpviewer_keywords:
- PRJ0041
ms.assetid: dc9f4cf9-6bd5-4222-89e8-7802a59bb96b
ms.openlocfilehash: dc6b36e052d3402f047257a4bf0035d7ec30f92a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206449"
---
# <a name="project-build-warning-prj0041"></a>プロジェクト ビルドの警告 PRJ0041

ファイル ' file ' の依存関係 ' dependency ' が見つかりません。 プロジェクトは引き続きビルドされる場合がありますが、このファイルが見つかるまでは引き続き期限切れになる可能性があります。

たとえば、ファイル (リソースファイルまたは .idl/odl ファイル) に、プロジェクトシステムが解決できない include ステートメントが含まれています。

プロジェクトシステムがプリプロセッサステートメント (#if など) を処理しないため、実際には、問題のあるステートメントがビルドに含まれないことがあります。

この警告を解決するには、.rc ファイル内の不要なコードをすべて削除するか、適切な名前のプレースホルダーファイルを追加します。
