---
title: 定義済みのシンボル ID
ms.date: 11/04/2016
helpviewer_keywords:
- symbols [C++], predefined IDs
- predefined symbol IDs
ms.assetid: 91a5d610-1a04-47e8-b8a4-63ad650a90df
ms.openlocfilehash: cb2f80315e0480c3fcb73092123cad88712dff05
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477299"
---
# <a name="predefined-symbol-ids"></a>定義済みのシンボル ID

新しいプロジェクトを開始する時点で、ユーザーが使用できるように、プロジェクトの種類に応じていくつかのシンボル ID が事前に定義されています。 これらのシンボル ID は、MFC など、さまざまなライブラリとプロジェクトの種類をサポートします。 これらのシンボル ID は、アプリケーションに通常含まれている共通のタスクか、マウスやポインターなどのハードウェア アイテムのアクションを表します。

これらのシンボル ID は、リソースを使用する際に重要になります。 また、アクセラレータ テーブルを編集するときにも使用できます。既に仮想キーに関連付けられているシンボル ID もあります。 手順で利用可能なことも、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。 定義済みの任意のシンボル ID を新しいリソースに割り当てたり、これらのシンボル ID にアクセラレータ キーを割り当てたりできます。シンボル ID に関連付けられている機能は、自動的にそのキーの組み合わせに関連付けられます。

これらのライブラリには、プロジェクトの一部として表示される以下の定義済みのシンボルがあります。

- [MFC の定義済みシンボル](../windows/mfc-predefined-symbols.md)

- [ATL の定義済みシンボル](../windows/atl-predefined-symbols.md)

- [Win32 の定義済みシンボル](../windows/win32-predefined-symbols.md)

   > [!NOTE]
   > 定義済みのシンボルは、常に読み取り専用です。

## <a name="requirements"></a>必要条件

Win32、MFC、または ATL

## <a name="see-also"></a>関連項目

[シンボル: リソース識別子](../windows/symbols-resource-identifiers.md)