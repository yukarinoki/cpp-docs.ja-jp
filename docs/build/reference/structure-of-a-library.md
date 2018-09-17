---
title: ライブラリの構造 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- libraries, structure
ms.assetid: a5fda8e8-4a1b-4499-9095-0df935262ce4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 03c2c66d45ee415ddc4f3ba27b6a100c5e2ec1dc
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702105"
---
# <a name="structure-of-a-library"></a>ライブラリの構造

ライブラリには、COFF オブジェクトが含まれています。 ライブラリ内のオブジェクトには、関数とプログラムの他のオブジェクトで外部から参照できるデータが含まれます。 ライブラリ内のオブジェクトは、ライブラリのメンバーとも呼ばれます。

/LINKERMEMBER オプションを使用して、DUMPBIN ツールを実行して、ライブラリの内容に関する追加情報を取得できます。 このオプションの詳細については、次を参照してください。 [DUMPBIN リファレンス](../../build/reference/dumpbin-reference.md)します。

## <a name="see-also"></a>関連項目

[LIB の概要](../../build/reference/overview-of-lib.md)