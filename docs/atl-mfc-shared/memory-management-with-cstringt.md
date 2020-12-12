---
description: 詳細については、「CStringT によるメモリ管理」を参照してください。
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
ms.openlocfilehash: 8306159aac44a2a8185052880459c9150b0cfda2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166929"
---
# <a name="memory-management-with-cstringt"></a>CStringT を使用したメモリ管理

クラス [CStringT](../atl-mfc-shared/reference/cstringt-class.md) は、可変長文字列を操作するために使用されるテンプレートクラスです。 これらの文字列を保持するメモリは、の各インスタンスに関連付けられている文字列マネージャーオブジェクトを通じて割り当てられ、解放され `CStringT` ます。 MFC と ATL は、、、およびと呼ばれるの既定のインスタンス化を提供し `CStringT` `CString` `CStringA` `CStringW` ます。これは、さまざまな文字型の文字列を操作します。 これらの文字型の型は、 **`char`** それぞれ TCHAR、、および **`wchar_t`** です。 これらの既定の文字列型では、プロセスヒープ (ATL の場合) または CRT ヒープ (MFC の場合) からメモリを割り当てる文字列マネージャーが使用されます。 一般的なアプリケーションでは、このメモリ割り当てスキームで十分です。 ただし、文字列 (またはマルチスレッドコード) を頻繁に使用するコードでは、既定のメモリマネージャーが最適に動作しない可能性があります。 このトピックでは、の既定のメモリ管理動作をオーバーライドして、手動でタスク用に最適化されたアロケーターを作成する方法について説明し `CStringT` ます。

- [カスタム文字列マネージャー (基本メソッド) の実装](../atl-mfc-shared/implementation-of-a-custom-string-manager-basic-method.md)

- [ヒープ競合の回避](../atl-mfc-shared/avoidance-of-heap-contention.md)

- [カスタム文字列マネージャー (高度なメソッド) の実装](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md)

- [CFixedStringT: カスタム文字列マネージャーの例](../atl-mfc-shared/cfixedstringt-example-of-a-custom-string-manager.md)

## <a name="see-also"></a>関連項目

[CustomString サンプル](../overview/visual-cpp-samples.md)
