---
title: 式エバリュエーター エラー CXX0039
ms.date: 11/04/2016
f1_keywords:
- CXX0039
helpviewer_keywords:
- CXX0039
- CAN0039
ms.assetid: 8bf698d2-e015-4595-944f-72b81aa43d22
ms.openlocfilehash: 5706d002eb3d566d05b059cb04b6b1626fdb3d33
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185127"
---
# <a name="expression-evaluator-error-cxx0039"></a>式エバリュエーター エラー CXX0039

シンボルがあいまいです

C 式エバリュエーターは、式で使用するシンボルのインスタンスを特定できません。 シンボルが継承ツリー内で複数回出現しています。

式で使用するインスタンスを明示的に指定するには、スコープ解決演算子 (`::`) を使用する必要があります。

このエラーは CAN0039 と同じです。
