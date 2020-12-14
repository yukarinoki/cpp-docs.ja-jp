---
description: 詳細については、「メモリ管理」を参照してください。
title: メモリ管理
ms.date: 11/04/2016
helpviewer_keywords:
- memory [MFC]
- MFC, memory management
- memory allocation [MFC]
- memory [MFC], managing
- memory allocation [MFC], MFC
ms.assetid: 934ac81b-d630-4232-88e5-ea74f7187987
ms.openlocfilehash: 4e274820ce82cf8b338c6a62349440e944f21f7a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253378"
---
# <a name="memory-management"></a>メモリ管理

この記事のグループでは、メモリ管理に関連する Microsoft Foundation Class ライブラリ (MFC) の汎用サービスを活用する方法について説明します。 メモリ割り当ては、フレーム割り当てとヒープ割り当てという2つの主なカテゴリに分けることができます。

2つの割り当て方法の主な違いの1つは、フレーム割り当てでは、通常は実際のメモリブロック自体を使用しますが、ヒープ割り当てでは常にメモリブロックへのポインターを指定するということです。 2つのスキームの大きな違いは、フレームオブジェクトが自動的に削除されるのに対し、ヒープオブジェクトはプログラマが明示的に削除する必要があることです。

Windows 用プログラムのメモリ管理に関する MFC 以外の情報については、Windows SDK の「 [メモリ管理](/windows/win32/memory/memory-management) 」を参照してください。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [フレーム割り当て](memory-management-frame-allocation.md)

- [ヒープ割り当て](memory-management-heap-allocation.md)

- [配列にメモリを割り当てる](memory-management-examples.md)

- [ヒープからの配列のメモリの解放](memory-management-examples.md)

- [データ構造のメモリの割り当て](memory-management-examples.md)

- [オブジェクトのメモリの割り当て](memory-management-examples.md)

- [サイズ変更可能メモリブロック](memory-management-resizable-memory-blocks.md)

## <a name="see-also"></a>関連項目

[概念](mfc-concepts.md)<br/>
[MFC の一般的なトピック](general-mfc-topics.md)
