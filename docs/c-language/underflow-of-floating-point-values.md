---
title: 浮動小数点値のアンダーフロー | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 78af8016-643c-47db-b4f1-7f06cb4b243e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4ceaa41dcaca88c7857a03c16ccccabdba086fd0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32387825"
---
# <a name="underflow-of-floating-point-values"></a>浮動小数点値のアンダーフロー
**ANSI 4.5.1** 数値演算関数がアンダーフロー エラー時に、整数式 `errno` を `ERANGE` マクロの値に設定するかどうか  
  
 浮動小数点アンダーフローは、式 `errno` を `ERANGE` に設定しません。 値がゼロに近づき、最終的にアンダーフローすると、値はゼロに設定されます。  
  
## <a name="see-also"></a>参照  
 [ライブラリ関数](../c-language/library-functions.md)