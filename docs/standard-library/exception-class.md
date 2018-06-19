---
title: exception クラス | Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- exception
dev_langs:
- C++
helpviewer_keywords:
- exception class
ms.assetid: 4f181f67-5888-4b50-89a6-745091ffb2fe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff6bc46fb8776de5f93b623b98f87513e710c603
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33843107"
---
# <a name="exception-class"></a>exception クラス

このクラスは、特定の式と C++ 標準ライブラリによってスローされたすべての例外の基底クラスとして機能します。

## <a name="syntax"></a>構文

```cpp
class exception {
   public:
   exception();
   exception(const char* const &message);
   exception(const char* const &message, int);
   exception(const exception &right);
   exception& operator=(const exception &right);
   virtual ~exception();
   virtual const char *what() const;
   };
```

## <a name="remarks"></a>コメント

具体的には、この基底クラスは [\<stdexcept >](../standard-library/stdexcept.md) で定義されている標準的な例外クラスのルートです。 `what` によって返される C の文字列値は、既定のコンストラクターによって未指定のまま残されますが、特定の派生クラスのコンストラクターによって実装定義された C の文字列として定義される場合があります。 このメンバー関数は、いずれも例外をスローしません。

`int` パラメーターでは、メモリを割り当てる必要がないことを指定できます。 `int` の値は無視されます。

> [!NOTE]
> コンストラクター `exception(const char* const &message)` と `exception(const char* const &message, int)` は、C++ 標準ライブラリに対する Microsoft 拡張機能です。

## <a name="example"></a>例

`exception` クラスから継承する標準の例外クラスの使用例については、[\<stdexcept>](../standard-library/stdexcept.md) で定義されているクラスを参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** \<exception>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
