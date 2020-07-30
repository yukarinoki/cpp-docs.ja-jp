---
title: コマンド ラインの警告 D9041
ms.date: 11/04/2016
f1_keywords:
- D9041
helpviewer_keywords:
- D9041
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
ms.openlocfilehash: e685e9bd0ffb58065f20f466131f8894baaf359f
ms.sourcegitcommit: 6e55aeb538b1c39af754f82d6f7738a18f5aa031
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87389728"
---
# <a name="command-line-warning-d9041"></a>コマンド ラインの警告 D9041

> '/*option-name*' の値 '*option-value*' が無効です。'*仮定値 ' と*想定します。この警告を指定するときに、コマンドラインオプションに '/analyze ' を追加します

**`/wd`** **`/we`** **`/wo`** **`/wl`** コマンドラインオプションを指定せずに、、、、またはコマンドラインオプションにコード分析の警告番号が追加されました **`/analyze`** 。 このエラーを解決するには、 **`/analyze`** コマンドラインオプションを追加するか、適切なコマンドラインオプションから無効な警告番号を削除し **`/w`** ます。

## <a name="example"></a>例

次のコマンドラインの例では、警告 D9041 が生成されます。

```cmd
cl /EHsc /LD /wd6001 filename.cpp
```

この警告を修正するには、 **`/analyze`** コマンドラインオプションを追加します。 **`/analyze`** ご使用のバージョンのコンパイラでがサポートされていない場合は、オプションから無効な警告番号を削除して **`/wd`** ください。

## <a name="see-also"></a>関連項目

[コマンド ライン エラー D8000 から D9999](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)<br/>
[MSVC コンパイラ オプション](../../build/reference/compiler-options.md)
