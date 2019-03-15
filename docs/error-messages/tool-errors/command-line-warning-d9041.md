---
title: コマンド ラインの警告 D9041
ms.date: 11/04/2016
f1_keywords:
- D9041
helpviewer_keywords:
- D9041
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
ms.openlocfilehash: 2311c61c4d661d58302308f06b08971f94cdacab
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57816309"
---
# <a name="command-line-warning-d9041"></a>コマンド ラインの警告 D9041

無効な値 'value' を '/option';'value'; と仮定した場合追加 '/analyze ' をこの警告を指定するときに、コマンド ライン オプション

コード分析の警告番号が追加、 **/wd**、 **/we**、 **/wo**、または **/wl**も、を指定せずにコマンドラインオプション **/analyze**コマンド ライン オプション。 このエラーを解決するには追加するか、 **/analyze**コマンド ライン オプション、または適切なから無効な警告番号を削除 **/w**コマンド ライン オプション。

## <a name="example"></a>例

次のコマンドラインの例では、警告 D9041 が生成されます。

```
cl /EHsc /LD /wd6001 filename.cpp
```

警告を解決するには、追加、 **/analyze**コマンド ライン オプション。 場合 **/analyze**はコンパイラのバージョンではサポートされていませんから無効な警告番号を削除、 **/wd**オプション。

## <a name="see-also"></a>関連項目

[コマンド ライン エラー D8000 から D9999](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)<br/>
[MSVC コンパイラ オプション](../../build/reference/compiler-options.md)