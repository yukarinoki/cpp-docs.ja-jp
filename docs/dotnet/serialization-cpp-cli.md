---
title: シリアル化 (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- serialization [C++]
- SerializableAttribute class, managed applications
- NonSerializedAttribute class, managed applications
- managed code [C++], serializing
- .NET Framework [C++], serialization
- serialization [C++], about serialization
ms.assetid: 869010ca-74e1-4989-b409-4643cdb94084
ms.openlocfilehash: b2dfdcaf1a1f33e89d106d4529ffc9af2d08376b
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545163"
---
# <a name="serialization-ccli"></a>シリアル化 (C++/CLI)

マネージクラス (個々のフィールドまたはプロパティを含む) のシリアル化 (オブジェクトまたはメンバーの状態を保存するプロセス) は、<xref:System.SerializableAttribute> クラスと <xref:System.NonSerializedAttribute> クラスでサポートされています。

## <a name="remarks"></a>コメント

**SerializableAttribute**カスタム属性をマネージクラスに適用して、クラス全体をシリアル化するか、特定のフィールドまたはプロパティのみを適用してマネージクラスの一部をシリアル化します。 **NonSerializedAttribute**カスタム属性を使用して、マネージクラスのフィールドまたはプロパティをシリアル化から除外します。

## <a name="example"></a>例

### <a name="description"></a>説明

次の例では、クラス `MyClass` (およびプロパティ `m_nCount`) は serializable としてマークされています。 ただし、`m_nData` プロパティはシリアル化されていない**カスタム属性**で示されているようにシリアル化されません。

### <a name="code"></a>コード

```cpp
// serialization_and_mcpp.cpp
// compile with: /LD /clr
using namespace System;

[ Serializable ]
public ref class MyClass {
public:
   int m_nCount;
private:
   [ NonSerialized ]
   int m_nData;
};
```

### <a name="comments"></a>コメント

どちらの属性も、"短い名前" (**Serializable**およびシリアル化され**てい**ない) を使用して参照できます。 これについては、「[属性の適用](/dotnet/standard/attributes/applying-attributes)」で詳しく説明します。

## <a name="see-also"></a>参照

[C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
