---
description: 詳細については、「シリアル化 (C++/CLI)」を参照してください。
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
ms.openlocfilehash: 1524ed5d4a000d2006f6f830b1d82119d170c3b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164602"
---
# <a name="serialization-ccli"></a>シリアル化 (C++/CLI)

マネージクラス (個々のフィールドまたはプロパティを含む) のシリアル化 (オブジェクトまたはメンバーの状態を保存するプロセス) は、クラスおよびクラスでサポートされてい <xref:System.SerializableAttribute> <xref:System.NonSerializedAttribute> ます。

## <a name="remarks"></a>解説

**SerializableAttribute** カスタム属性をマネージクラスに適用して、クラス全体をシリアル化するか、特定のフィールドまたはプロパティのみを適用してマネージクラスの一部をシリアル化します。 **NonSerializedAttribute** カスタム属性を使用して、マネージクラスのフィールドまたはプロパティをシリアル化から除外します。

## <a name="example"></a>例

### <a name="description"></a>説明

次の例では、クラス `MyClass` (およびプロパティ `m_nCount` ) は serializable としてマークされています。 ただし、シリアル `m_nData` 化されていないカスタム属性で示されているように、プロパティはシリアル化されません。

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

### <a name="comments"></a>説明

どちらの属性も、"短い名前" (**Serializable** およびシリアル化され **てい** ない) を使用して参照できます。 これについては、「 [属性の適用](/dotnet/standard/attributes/applying-attributes)」で詳しく説明します。

## <a name="see-also"></a>関連項目

[C++/CLI を使用した .NET プログラミング (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
