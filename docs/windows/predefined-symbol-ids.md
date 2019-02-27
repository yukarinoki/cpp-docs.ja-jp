---
title: 定義済みのシンボル ID
ms.date: 02/14/2019
helpviewer_keywords:
- symbols [C++], predefined IDs
- predefined symbol IDs
ms.assetid: 91a5d610-1a04-47e8-b8a4-63ad650a90df
ms.openlocfilehash: 7d3581a9f6f2a2080f72634a01d3417ffecf82a4
ms.sourcegitcommit: f127b08f114b8d6cab6b684febcb6f2ae0e055ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/27/2019
ms.locfileid: "56954914"
---
# <a name="predefined-symbol-ids"></a>定義済みのシンボル ID

新しいプロジェクトを開始する時点で、ユーザーが使用できるように、プロジェクトの種類に応じていくつかのシンボル ID が事前に定義されています。 これらのシンボル ID は、MFC など、さまざまなライブラリとプロジェクトの種類をサポートします。 これらのシンボル ID は、アプリケーションに通常含まれている共通のタスクか、マウスやポインターなどのハードウェア アイテムのアクションを表します。

これらのシンボル ID は、リソースを使用する際に重要になります。 アクセラレータ テーブルを編集すると、既に仮想キーに関連付けられているそれらの一部では利用です。 介して利用可能にもなる、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。 定義済みシンボル Id のいずれかを新しいリソースに割り当てることができますか、アクセラレータ キーと ID は、そのキーの組み合わせを自動的に関連付けますシンボルに関連付けられている機能に割り当てることができます。

これらのライブラリには、プロジェクトの一部として表示される以下の定義済みのシンボルがあります。

- [ATL の定義済みシンボル](../windows/atl-predefined-symbols.md)

- [MFC の定義済みシンボル](../windows/mfc-predefined-symbols.md)

- [Win32 の定義済みシンボル](../windows/win32-predefined-symbols.md)

> [!NOTE]
> 定義済みのシンボルは、常に読み取り専用です。

## <a name="requirements"></a>必要条件

Win32、MFC、または ATL

## <a name="see-also"></a>関連項目

[リソース識別子 (シンボル)](../windows/symbols-resource-identifiers.md)<br/>
[方法: シンボルの作成](../windows/creating-new-symbols.md)<br/>
[方法: シンボルの管理](../windows/changing-a-symbol-or-symbol-name-id.md)<br/>