---
title: コンパイラ エラー C3180 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3180
dev_langs:
- C++
helpviewer_keywords:
- C3180
ms.assetid: 5281f583-7df7-418a-8507-d4da67ed6572
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e200a75164c0d7fdb0c6804d084630cc6e6007e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048371"
---
# <a name="compiler-error-c3180"></a>コンパイラ エラー C3180

'type name': 名前がメタデータ制限の 'limit' 文字を超えています

コンパイラでは、メタデータ内のマネージ型の名前が切り捨てられます。 切り捨てによりは、型を使用できない、`#using`ディレクティブ (または別の言語と同等)。

型名の制限には、任意の名前空間の修飾が含まれています。