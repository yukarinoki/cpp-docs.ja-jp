---
description: 詳細については、「コンパイラエラー C2220」を参照してください。
title: コンパイラ エラー C2220
ms.date: 11/04/2016
f1_keywords:
- C2220
helpviewer_keywords:
- C2220
ms.assetid: d610802c-64d7-40ad-a2a6-0ed0b6815a6c
ms.openlocfilehash: f45a34d0cdaa5e82c3f5e6c051126c6df4eb2005
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245435"
---
# <a name="compiler-error-c2220"></a>コンパイラ エラー C2220

warning treated as error - no object file generated

[/Wx](../../build/reference/compiler-option-warning-level.md) は、すべての警告をエラーとして扱うようにコンパイラに指示します。 エラーが発生したため、オブジェクトまたは実行可能ファイルは生成されませんでした。

このエラーは、 **/wx** フラグが設定されており、コンパイル中に警告が発生した場合にのみ表示されます。 このエラーを解決するには、プロジェクトのすべての警告を除去する必要があります。

### <a name="to-fix-use-one-of-the-following-techniques"></a>解決するには、次のいずれかの手法を使用します。

- プロジェクトの警告の原因となった問題を解決します。

- 低い警告レベルでコンパイルします。たとえば、 **/W4** の代わりに **/W3** を使用します。

- [警告](../../preprocessor/warning.md)プラグマを使用して、特定の警告を無効または非表示にします。

- **/Wx** を使用してコンパイルしないでください。
