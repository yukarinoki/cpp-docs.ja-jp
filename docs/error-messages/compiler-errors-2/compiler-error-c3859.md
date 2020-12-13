---
description: 詳細については、「コンパイラエラー C3859」を参照してください。
title: コンパイラ エラー C3859
ms.date: 03/08/2019
f1_keywords:
- C3859
helpviewer_keywords:
- C3859
ms.assetid: 40e93b25-4393-4467-90de-035434a665c7
ms.openlocfilehash: 25c05425072cda6924d90f08c9aeff7446a4e85b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336114"
---
# <a name="compiler-error-c3859"></a>コンパイラ エラー C3859

> PCH の仮想メモリの範囲を超えました。'-Zm *value*' 以上のコマンドラインオプションを使用して再コンパイルしてください

プリコンパイル済みヘッダーに割り当てられた仮想メモリが、コンパイラが配置しようとしているデータ量に対して小さすぎます。 Visual Studio 2015 以降、 **/zm** 推奨事項は、ディレクティブを使用する場合にのみ意味があり `#pragma hdrstop` ます。 それ以外の場合は、Windows 仮想メモリの負荷の問題を示す誤ったエラーになります。

プリコンパイル済みヘッダーでディレクティブが使用されている場合は、 `#pragma hdrstop` **/zm** コンパイラフラグを使用して、プリコンパイル済みヘッダーファイルにより大きな値を指定します。 それ以外の場合は、ビルド内の並列コンパイルプロセスの数を減らすことを検討してください。 詳細については、「 [/zm (プリコンパイル済みヘッダーのメモリ割り当て制限の指定)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md)」を参照してください。
