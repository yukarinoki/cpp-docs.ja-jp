---
description: '詳細情報: 静的メンバー (C++)'
title: 静的メンバー (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- class members [C++], static
- instance constructors, static members
- class members [C++], shared
- members [C++], static data members
- static members [C++], data members
- static data members [C++]
- data members [C++], static data members
- class instances [C++], shared members
- instance constructors, shared members
- class instances [C++], static members
ms.assetid: 9cc8cf0f-d74c-46f2-8e83-42d4e42c8370
ms.openlocfilehash: 2aad7c5ef70f319a976704ef36664459ca9ab252
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317949"
---
# <a name="static-members-c"></a>静的メンバー (C++)

クラスには、静的なメンバー データとメンバー関数を含めることができます。 データメンバーがとして宣言されている場合 **`static`** 、クラスのすべてのオブジェクトに対してデータのコピーが1つだけ保持されます。

静的データ メンバーは、特定のクラス型のオブジェクトの一部ではありません。 その結果、静的データ メンバーの宣言は定義とは見なされません。 データ メンバーはクラス スコープで宣言されますが、定義はファイル スコープで行われます。 これらの静的メンバーは外部リンケージを持ちます。 次に例を示します。

```cpp
// static_data_members.cpp
class BufferedOutput
{
public:
   // Return number of bytes written by any object of this class.
   short BytesWritten()
   {
      return bytecount;
   }

   // Reset the counter.
   static void ResetCount()
   {
      bytecount = 0;
   }

   // Static member declaration.
   static long bytecount;
};

// Define bytecount in file scope.
long BufferedOutput::bytecount;

int main()
{
}
```

上記のコードで、メンバー `bytecount` は、クラス `BufferedOutput` で宣言されていますが、クラス宣言の外側で定義する必要があります。

静的データ メンバーは、クラス型のオブジェクトを参照せずに参照できます。 `BufferedOutput` オブジェクトを使用して書き込まれたバイト数は、次のように取得できます。

```cpp
long nBytes = BufferedOutput::bytecount;
```

静的メンバーを存在させるために、クラス型のオブジェクトが存在する必要はありません。 静的メンバーには、メンバー選択 () を使用してアクセスすることもでき **ます。** and **->** ) 演算子。 次に例を示します。

```cpp
BufferedOutput Console;

long nBytes = Console.bytecount;
```

前のケースでは、オブジェクト (`Console`) への参照は評価されません。返される値は、静的オブジェクト `bytecount` の値です。

静的データ メンバーはクラス メンバーのアクセス規則に従うため、静的データ メンバーへのプライベート アクセスはクラス メンバー関数およびフレンドだけに許可されます。 これらの規則については [、「メンバー-Access Control](../cpp/member-access-control-cpp.md)」を参照してください。 例外は、静的データ メンバーが、そのアクセス制限にかかわらず、ファイルのスコープ内で定義されなければならないということです。 データ メンバーを明示的に初期化する場合は、初期化子を定義で指定する必要があります。

静的メンバーの型は、クラス名で修飾されていません。 したがって、の型 `BufferedOutput::bytecount` は **`long`** です。

## <a name="see-also"></a>関連項目

[クラスと構造体](../cpp/classes-and-structs-cpp.md)
