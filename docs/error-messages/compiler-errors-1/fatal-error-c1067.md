---
title: 致命的なエラー C1067 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1067
dev_langs:
- C++
helpviewer_keywords:
- C1067
ms.assetid: e2c94be6-4573-4571-aac9-73d657fe9f96
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f267e58617fbc68835fd3a387c4b635de4fd0530
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077673"
---
# <a name="fatal-error-c1067"></a>致命的なエラー C1067

コンパイラの制限: 型のレコード サイズ 64 K の制限を超えました

シンボルは、247 文字を超える装飾の名前を持つ場合、このエラーが発生する可能性があります。  を解決するには、シンボル名を短きます。

コンパイラは、デバッグ情報を生成するときに、ソース コードで検出された型を定義するタイプのレコードを出力します。  たとえば、型のレコードには、単純な構造体と関数の引数リストが含まれます。  これらの種類のレコードの一部には、大きい一覧ができます。

任意の種類のレコードのサイズを 64 K に制限があります。  その 64 K の制限を超えた場合、このエラーが発生します。

C1067 は、長い名前のシンボルの数がある場合、またはクラス、構造体、または共用体がメンバーが多すぎる場合にも発生します。