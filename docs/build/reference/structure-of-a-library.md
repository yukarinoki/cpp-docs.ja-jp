---
title: ライブラリの構造 |Microsoft ドキュメント
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
ms.openlocfilehash: 6eff0000aef01790106b44b49b4855218fcf9332
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="structure-of-a-library"></a>ライブラリの構造
ライブラリには、COFF オブジェクトが含まれています。 オブジェクトをライブラリには、関数とプログラムの他のオブジェクトで外部から参照可能なデータを含めます。 ライブラリ内のオブジェクトは、ライブラリのメンバーとも呼ばれます。  
  
 /LINKERMEMBER オプションを使用して、DUMPBIN ツールを実行して、ライブラリの内容に関する追加情報を取得できます。 詳細については、このオプションは、次を参照してください。 [DUMPBIN リファレンス](../../build/reference/dumpbin-reference.md)です。  
  
## <a name="see-also"></a>関連項目  
 [LIB の概要](../../build/reference/overview-of-lib.md)