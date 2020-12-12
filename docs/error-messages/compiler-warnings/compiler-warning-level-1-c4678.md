---
description: '詳細情報: コンパイラの警告 (レベル 1) C4678'
title: コンパイラの警告 (レベル 1) C4678
ms.date: 11/04/2016
f1_keywords:
- C4678
helpviewer_keywords:
- C4678
ms.assetid: 0c588f34-595d-4e5c-9470-8723fca2cc06
ms.openlocfilehash: a590bd03ba73fc4f8d5421727e5e35ac1384ffaa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285384"
---
# <a name="compiler-warning-level-1-c4678"></a>コンパイラの警告 (レベル 1) C4678

基底クラス 'base_type' のアクセス可能性が 'derived_type' よりも小さいです。

パブリック型は、プライベート型から派生します。 参照されたアセンブリでパブリック型がインスタンス化される場合は、プライベート基本型のメンバーにアクセスできません。

C4678 は、互換性のために残されているコンパイラオプション **/clr: oldSyntax** を使用してのみ到達可能です。 **/Clr** を使用すると、派生クラスよりもアクセスが困難な基底クラスを持つことになります。
