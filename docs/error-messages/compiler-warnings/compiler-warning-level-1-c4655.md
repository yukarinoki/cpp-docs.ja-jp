---
description: '詳細情報: コンパイラの警告 (レベル 1) C4655'
title: コンパイラの警告 (レベル 1) C4655
ms.date: 08/27/2018
f1_keywords:
- C4655
helpviewer_keywords:
- C4655
ms.assetid: 540f2c7a-e4a1-49af-84b4-03eeea1bbf41
ms.openlocfilehash: 2573ac5410114a0fe4ff4b074b83bbbb2efc8c97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318787"
---
# <a name="compiler-warning-level-1-c4655"></a>コンパイラの警告 (レベル 1) C4655

> '*symbol*': 変数の型が前回のビルド以降の新しいものであるか、別の場所で定義されています

## <a name="remarks"></a>解説

前回成功したビルド以降に、新しいデータ型が変更または追加されています。 エディット コンティニュは、既存のデータ型への変更をサポートしません。

この警告の後に、 [致命的なエラー C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md)が生成されます。 詳細については、「 [サポートされているコード変更](/visualstudio/debugger/supported-code-changes-cpp)」を参照してください。

### <a name="to-remove-this-warning-without-ending-the-current-debug-session"></a>現在のデバッグ セッションを終了せずにこの警告を削除するには

1. データ型をエラーが起こる前の状態に戻します。

2. **[デバッグ]** メニューの **[コード変更を適用]** をクリックします。

### <a name="to-remove-this-warning-without-changing-your-source-code"></a>ソース コードを変更せずにこの警告を削除するには

1. **[デバッグ]** メニューの **[デバッグの停止]** をクリックします。

2. **[ビルド]** メニューの **[ビルド]** をクリックします。
