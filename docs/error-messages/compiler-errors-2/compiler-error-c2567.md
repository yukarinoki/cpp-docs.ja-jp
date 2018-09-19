---
title: コンパイラ エラー C2567 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2567
dev_langs:
- C++
helpviewer_keywords:
- C2567
ms.assetid: 9c140ac9-7059-47e6-9ba1-e7939c8c0dc3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb09aacc1b81e9f0e0c9c96a496eccc89a061f37
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46104242"
---
# <a name="compiler-error-c2567"></a>コンパイラ エラー C2567

'file' のメタデータを開くことができません、ファイルが削除されたか移動

ソースで参照されたメタデータ ファイル (と`#using`) が見つかりませんでした同じディレクトリにコンパイラのバック エンドのプロセスによって、コンパイラ フロント エンドのプロセスであったためです。 参照してください[#using ディレクティブ](../../preprocessor/hash-using-directive-cpp.md)詳細についてはします。

使用してコンパイルする場合に C2567 が考えられます **/c**いずれかでコンピューターし、別のコンピューター上のリンク時コード生成を試みます。 詳細については、次を参照してください。 [/LTCG (リンク時コード生成)](../../build/reference/ltcg-link-time-code-generation.md))。

コンピューターのメモリ不足であることを示すも可能性があります。

このエラーを修正するには、ビルド プロセスのすべてのフェーズのメタデータ ファイルは同じディレクトリの場所にいることを確認します。