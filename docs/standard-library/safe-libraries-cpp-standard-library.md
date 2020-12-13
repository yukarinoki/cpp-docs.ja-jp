---
description: '詳細情報: 安全なライブラリ: C++ 標準ライブラリ'
title: '安全なライブラリ: C++ 標準ライブラリ'
ms.date: 11/04/2016
helpviewer_keywords:
- Safe Libraries
- Safe Libraries, C++ Standard Library
- Safe C++ Standard Library
ms.assetid: 3993340f-1f29-4d81-b3f5-52a52bc8e148
ms.openlocfilehash: 7027031054bf9ef7c2a157d6162539bc3801dec4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148890"
---
# <a name="safe-libraries-c-standard-library"></a>安全なライブラリ: C++ 標準ライブラリ

Microsoft C++ に付属するライブラリ (C++ 標準ライブラリを含む) には、セキュリティを強化するために、いくつかの機能強化が施されています。

C++ 標準ライブラリに含まれる一部のメソッドは、バッファー オーバーランが発生する可能性のあるものや、コードに欠陥があることによる潜在的な危険性が確認されています。 こうしたメソッドの使用はお勧めできません。また、それらに置き換わる、新しい安全性の高いメソッドが作成されています。 これに該当する新しいメソッドのすべてには、末尾に `_s`が付いています。

反復子とアルゴリズムにも、安全性を向上するためのいくつかの機能強化が行われています。 詳細については、「 [Checked Iterators](../standard-library/checked-iterators.md)」、「 [Debug Iterator Support](../standard-library/debug-iterator-support.md) 」、および「 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)」を参照してください。

## <a name="remarks"></a>解説

次の表に、潜在的な危険性のある C++ 標準ライブラリのメソッドと、それと同等な安全なメソッドを示します。

|潜在的に危険なメソッド|安全な同等のメソッド|
|-------------------------------|----------------------|
|[copy](../standard-library/basic-string-class.md#copy)|[basic_string:: _Copy_s](../standard-library/basic-string-class.md#copy_s)|
|[copy](../standard-library/char-traits-struct.md#copy)|[char_traits::_Copy_s](../standard-library/char-traits-struct.md#copy_s)|

上記の潜在的に危険なメソッドのいずれかを呼び出したり、不適切に反復子を使用したりすると、コンパイラは[コンパイラの警告 (レベル 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) を生成します。 これらの警告を無効にする方法の詳細については、「 [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md)」を参照してください。

## <a name="in-this-section"></a>このセクションの内容

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)

[_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md)

[チェックを行う反復子](../standard-library/checked-iterators.md)

[反復子のデバッグのサポート](../standard-library/debug-iterator-support.md)

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリの概要](../standard-library/cpp-standard-library-overview.md)
