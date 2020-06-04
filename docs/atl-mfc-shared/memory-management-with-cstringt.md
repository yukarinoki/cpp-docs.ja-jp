---
title: CStringT を使用したメモリ管理
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects, memory management
- memory [C++], usage
- IAtlStringMgr class, using
- strings [C++], custom memory management
- CFixedStringT class, description of
- strings [C++], memory management
- CStringT class, memory management
ms.assetid: 88b8342d-19b5-48c4-9cf6-e4c44cece21e
ms.openlocfilehash: af042c80b9e3e0de872261f89255a26728b218cd
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440508"
---
# <a name="memory-management-with-cstringt"></a>CStringT を使用したメモリ管理

クラス[CStringT](../atl-mfc-shared/reference/cstringt-class.md)は、可変長文字列を操作するために使用されるテンプレートクラスです。 これらの文字列を保持するメモリは、`CStringT`の各インスタンスに関連付けられている文字列マネージャーオブジェクトを通じて割り当てられ、解放されます。 MFC と ATL は、さまざまな文字型の文字列を操作する `CString`、`CStringA`、および `CStringW`と呼ばれる `CStringT`の既定のインスタンス化を提供します。 これらの文字型の型は、それぞれ TCHAR、 **char**、および `wchar_t`です。 これらの既定の文字列型では、プロセスヒープ (ATL の場合) または CRT ヒープ (MFC の場合) からメモリを割り当てる文字列マネージャーが使用されます。 一般的なアプリケーションでは、このメモリ割り当てスキームで十分です。 ただし、文字列 (またはマルチスレッドコード) を頻繁に使用するコードでは、既定のメモリマネージャーが最適に動作しない可能性があります。 このトピックでは、`CStringT`の既定のメモリ管理動作をオーバーライドして、手動でタスク用に最適化されたアロケーターを作成する方法について説明します。

- [カスタム文字列マネージャーの実装 (基本方法)](../atl-mfc-shared/implementation-of-a-custom-string-manager-basic-method.md)

- [ヒープ競合の回避](../atl-mfc-shared/avoidance-of-heap-contention.md)

- [カスタム文字列マネージャーの実装 (詳細方法)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md)

- [CFixedStringT: カスタム文字列マネージャーの例](../atl-mfc-shared/cfixedstringt-example-of-a-custom-string-manager.md)

## <a name="see-also"></a>参照

[CustomString サンプル](../overview/visual-cpp-samples.md)
