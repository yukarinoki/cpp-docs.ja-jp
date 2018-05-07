---
title: CObject クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CObject
- AFX/CObject
- AFX/CObject::CObject
- AFX/CObject::AssertValid
- AFX/CObject::Dump
- AFX/CObject::GetRuntimeClass
- AFX/CObject::IsKindOf
- AFX/CObject::IsSerializable
- AFX/CObject::Serialize
dev_langs:
- C++
helpviewer_keywords:
- CObject [MFC], CObject
- CObject [MFC], AssertValid
- CObject [MFC], Dump
- CObject [MFC], GetRuntimeClass
- CObject [MFC], IsKindOf
- CObject [MFC], IsSerializable
- CObject [MFC], Serialize
ms.assetid: 95e9acd3-d9eb-4ac0-b52b-ca4a501a7a3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 38c27d2fa0e04770bae69901e1164da84c2186ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cobject-class"></a>CObject クラス
MFC ライブラリの重要な基底クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class AFX_NOVTABLE CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CObject::CObject](#cobject)|既定のコンストラクター|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Cobject::assertvalid](#assertvalid)|このオブジェクトの整合性を検証します。|  
|[CObject::Dump](#dump)|このオブジェクトの診断ダンプを生成します。|  
|[CObject::GetRuntimeClass](#getruntimeclass)|返します、`CRuntimeClass`このオブジェクトのクラスに対応する構造体。|  
|[使うため](#iskindof)|特定のクラスにこのオブジェクトのリレーションシップをテストします。|  
|[CObject::IsSerializable](#isserializable)|このオブジェクトをシリアル化できるかどうかどうかをテストします。|  
|[Cobject::serialize](#serialize)|ロードまたはアーカイブから/にオブジェクトを格納します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CObject::operator delete](#operator_delete)|特殊な**削除**演算子。|  
|[新しい CObject::operator](#operator_new)|特殊な**新しい**演算子。|  
  
## <a name="remarks"></a>コメント  
 などのライブラリのクラスだけでなく、ルートとして機能し`CFile`と`CObList`、記述するクラスについてもします。 `CObject` などの基本的なサービスを提供します  
  
-   シリアル化のサポート  
  
-   ランタイム クラス情報  
  
-   オブジェクトの診断出力  
  
-   コレクション クラスとの互換性  
  
 なお`CObject`多重継承をサポートしていません。 派生クラスには、1 つだけ持つことができます`CObject`基本クラス、およびを`CObject`階層の一番左にある必要があります。 許される、ただし、構造を持っていると非- `CObject`-多重継承の右側の分岐内のクラスを派生します。  
  
 主なメリットを実感`CObject`派生クラスの実装と宣言の省略可能なマクロの一部を使用する場合。  
  
 第 1 レベル マクロ[DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic)と[IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)クラス名と、階層内での位置への実行時アクセスを許可します。 さらに、これにより、意味のある診断ダンプします。  
  
 第 2 レベル マクロ[DECLARE_SERIAL](run-time-object-model-services.md#declare_serial)と[IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)で第 1 レベルのマクロのすべての機能を追加し、「シリアル化」と「アーカイブします」の間にオブジェクトを有効にする。  
  
 一般に Microsoft Foundation classes と C++ のクラスを派生することや使用についての`CObject`を参照してください[を使用して CObject](../../mfc/using-cobject.md)と[シリアル化](../../mfc/serialization-in-mfc.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CObject`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
  
##  <a name="assertvalid"></a>  Cobject::assertvalid  
 このオブジェクトの整合性を検証します。  
  
```  
virtual void AssertValid() const;  
```  
  
### <a name="remarks"></a>コメント  
 `AssertValid` 内部状態をチェックして、このオブジェクトの有効性チェックを実行します。 ライブラリのデバッグ バージョンで`AssertValid`アサートし、アサーションが失敗した行番号とファイル名を一覧表示するメッセージを使用してプログラムを終了したがって可能性があります。  
  
 オーバーライドする必要があります、独自のクラスを記述するときに、`AssertValid`自分や、クラスの他のユーザーの診断サービスを提供する関数。 オーバーライドされた`AssertValid`通常を呼び出す、`AssertValid`派生クラス独自のデータ メンバーをチェックする前に、基底クラスの関数。  
  
 `AssertValid`は、 **const**関数では、テスト中にオブジェクトの状態を変更する許可されていません。 派生クラス`AssertValid`関数が例外をスローする必要がありますが、無効なオブジェクト データを検出するかどうかではなくをアサートします。  
  
 「有効」の定義は、オブジェクトのクラスに依存します。 原則として、関数が、「簡易チェック」を実行します。 つまり、オブジェクトに他のオブジェクトへのポインターが含まれている場合ことを確認するかどうか、ポインター、null ではないポインターによって参照されるオブジェクトの有効性を実行する必要があります。  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`すべてで使用されるクラス`CObject`例です。  
  
 [!code-cpp[NVC_MFCCObjectSample#7](../../mfc/codesnippet/cpp/cobject-class_1.cpp)]  
  
 別の例では、次を参照してください。 [AfxDoForAllObjects](diagnostic-services.md#afxdoforallobjects)です。  
  
##  <a name="cobject"></a>  CObject::CObject  
 これらの関数は、標準`CObject`コンス トラクターです。  
  
```  
CObject();  
CObject(const CObject& objectSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 *objectSrc*  
 別の参照 `CObject`  
  
### <a name="remarks"></a>コメント  
 既定のバージョンは自動的には、派生クラスのコンス トラクターによって呼び出されます。  
  
 クラスがシリアル化可能な場合 (組み込まれています、`IMPLEMENT_SERIAL`マクロ)、クラス宣言に既定のコンス トラクター (引数なしのコンス トラクター) を持つ必要があります。 既定のコンス トラクターを必要がない場合、private を宣言または"empty"のコンス トラクターを保護します。 詳細については、次を参照してください。[を使用して CObject](../../mfc/using-cobject.md)です。  
  
 標準 C++ 既定クラスのコピー コンス トラクターは、メンバー間でコピーします。 プライベートのプレゼンス`CObject`クラスのコピー コンス トラクターが必要なのに使用できない場合、コピー コンス トラクターがコンパイラのエラー メッセージを保証します。 クラスは、この機能を必要とする場合は、コピー コンス トラクターを指定する必要がありますしたがってです。  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`で使用されるクラス、`CObject`例です。  
  
 [!code-cpp[NVC_MFCCObjectSample#8](../../mfc/codesnippet/cpp/cobject-class_2.cpp)]  
  
##  <a name="dump"></a>  CObject::Dump  
 オブジェクトの内容をダンプする[CDumpContext](../../mfc/reference/cdumpcontext-class.md)オブジェクト。  
  
```  
virtual void Dump(CDumpContext& dc) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `dc`  
 通常、ダンプの診断ダンプ コンテキスト`afxDump`です。  
  
### <a name="remarks"></a>コメント  
 オーバーライドする必要があります、独自のクラスを記述するときに、`Dump`自分や、クラスの他のユーザーの診断サービスを提供する関数。 オーバーライドされた`Dump`通常を呼び出す、`Dump`派生クラス独自のデータ メンバーを印刷する前に、基底クラスの関数。 `CObject::Dump` クラスで使用する場合は、クラス名を出力、`IMPLEMENT_DYNAMIC`または`IMPLEMENT_SERIAL`マクロです。  
  
> [!NOTE]
>  `Dump`関数がその出力の末尾に改行文字に出力することはありません。  
  
 `Dump` 呼び出しは、Microsoft Foundation Class ライブラリのデバッグ バージョンでのみ合理的です。 呼び出し、関数宣言と関数の実装を囲む必要があります **#ifdef _DEBUG** /  `#endif`の条件付きコンパイル ステートメントです。  
  
 `Dump`は、 **const**関数は、のダンプ中にオブジェクトの状態を変更する許可されていません。  
  
 [CDumpContext 挿入 (<<) 演算子](../../mfc/reference/cdumpcontext-class.md#operator_lt_lt)呼び出し`Dump`ときに、`CObject`ポインターを挿入します。  
  
 `Dump` オブジェクトののみ「無閉路有向」ダンプを許可します。 たとえば、オブジェクトの一覧をダンプすることができますが、スタックがオーバーフローする一方のオブジェクトが一覧自体の場合は、最終的には。  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`すべてで使用されるクラス`CObject`例です。  
  
 [!code-cpp[NVC_MFCCObjectSample#9](../../mfc/codesnippet/cpp/cobject-class_3.cpp)]  
  
##  <a name="getruntimeclass"></a>  CObject::GetRuntimeClass  
 返します、`CRuntimeClass`このオブジェクトのクラスに対応する構造体。  
  
```  
virtual CRuntimeClass* GetRuntimeClass() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)構造です。 このオブジェクトのクラスに対応することはありません**NULL**です。  
  
### <a name="remarks"></a>コメント  
 1 つを使用する必要がある`CRuntimeClass`構造`CObject`-クラスを派生します。 構造体のメンバーは次のとおりです。  
  
- **LPCSTR m_lpszClassName** ASCII クラス名を含む null で終わる文字列。  
  
- **int m_nObjectSize** (バイト単位)、オブジェクトのサイズ。 オブジェクトは、割り当てられたメモリを指すデータ メンバーが、そのメモリのサイズは含まれません。  
  
- **UINT m_wSchema**スキーマ番号 (のシリアル化できないクラスの 1)。 参照してください、 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)スキーマ番号の詳細についてはマクロです。  
  
- **CObject\* (PASCAL\* m_pfnCreateObject) に関するページ ()** クラスのオブジェクトを作成する既定のコンス トラクターへの関数ポインター (有効なクラスは、動的な作成をサポートする場合にのみ、それを返します**NULL**).  
  
- **CRuntimeClass\* (PASCAL\* m_pfn_GetBaseClass) に関するページ ()** 、アプリケーションは、MFC の AFXDLL バージョンを動的にリンクしている場合、関数へのポインターを返す、`CRuntimeClass`基底クラスの構造体。  
  
- **CRuntimeClass\* m_pBaseClass** 、アプリケーションが MFC へのポインターを静的にリンクされているかどうか、`CRuntimeClass`基底クラスの構造体。  
  
 この関数の使用を必要と、 [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)、 [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)、または[IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)マクロで、クラスの実装です。 そうしないと正しくない結果が表示されます。  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`すべてで使用されるクラス`CObject`例です。  
  
 [!code-cpp[NVC_MFCCObjectSample#10](../../mfc/codesnippet/cpp/cobject-class_4.cpp)]  
  
##  <a name="iskindof"></a>  使うため  
 特定のクラスにこのオブジェクトのリレーションシップをテストします。  
  
```  
BOOL IsKindOf(const CRuntimeClass* pClass) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pClass`  
 ポインター、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)構造に関連付けられている、 `CObject`-クラスを派生します。  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが、クラスに対応している場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数をテスト`pClass`するかどうか (1) は、指定したクラスのオブジェクト、または (2) は、指定したクラスから派生したクラスのオブジェクトを参照してください。 この機能で宣言されたクラスに対してのみ、 [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic)、 [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate)、または[DECLARE_SERIAL](run-time-object-model-services.md#declare_serial)マクロです。  
  
 C++ ポリモーフィズムの機能が活用できないためには、広範囲にこの関数を使用しないでください。 仮想関数を代わりに使用します。  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`すべてで使用されるクラス`CObject`例です。  
  
 [!code-cpp[NVC_MFCCObjectSample#11](../../mfc/codesnippet/cpp/cobject-class_5.cpp)]  
  
##  <a name="isserializable"></a>  CObject::IsSerializable  
 このオブジェクトはシリアル化の条件に適合するかどうかをテストします。  
  
```  
BOOL IsSerializable() const;  
```  
  
### <a name="return-value"></a>戻り値  
 この場合は 0 以外のオブジェクトをシリアル化できます。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 シリアル化できるクラスは、その宣言を含める必要があります、 [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial)マクロ、および実装を含める必要があります、 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)マクロです。  
  
> [!NOTE]
>  この関数は無効です。  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`すべてで使用されるクラス`CObject`例です。  
  
 [!code-cpp[NVC_MFCCObjectSample#12](../../mfc/codesnippet/cpp/cobject-class_6.cpp)]  
  
##  <a name="operator_delete"></a>  CObject::operator delete  
 ライブラリのリリース バージョンの演算子**削除**演算子によって割り当てられたメモリを解放**新しい**です。  
  
```  
void PASCAL operator delete(void* p);

 
void PASCAL operator delete(
    void* p,
    void* pPlace);

 
void PASCAL operator delete(
    void* p,  
    LPCSTR lpszFileName,  
    int nLine);
```  
  
### <a name="remarks"></a>コメント  
 デバッグ バージョンで演算子**削除**メモリ リークを検出するように設計割り当て監視のスキームに参加します。  
  
 コード行を使用する場合  
  
 [!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]  
  
 任意のコード行の前に、します。CPP ファイルの 3 番目のバージョン**削除**使用は割り当て済みのブロックを後でレポートをファイル名と行番号が格納されます。 余分なパラメーターを指定することについて心配する必要はありません。マクロをするを行います。  
  
 使用しない場合でも`DEBUG_NEW`リーク検出の取得がデバッグ モードで、上記で説明したソース ファイルの行番号のレポート作成しなくてもします。  
  
 演算子をオーバーライドする場合は**新しい**と**削除**、この診断機能が低下します。  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`で使用されるクラス、`CObject`例です。  
  
 [!code-cpp[NVC_MFCCObjectSample#15](../../mfc/codesnippet/cpp/cobject-class_8.cpp)]  
  
##  <a name="operator_new"></a>  新しい CObject::operator  
 ライブラリのリリース バージョンの演算子**新しい**と同様の方法で最適なメモリ割り当てを実行`malloc`です。  
  
```  
void* PASCAL operator new(size_t nSize);  
void* PASCAL operator new(size_t, void* p);

 
void* PASCAL operator new(
    size_t nSize,  
    LPCSTR lpszFileName,  
    int nLine);
```  
  
### <a name="remarks"></a>コメント  
 デバッグ バージョンで演算子**新しい**メモリ リークを検出するように設計割り当て監視のスキームに参加します。  
  
 コード行を使用する場合  
  
 [!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]  
  
 任意のコード行の前に、します。CPP ファイルの 2 番目のバージョン**新しい**使用は割り当て済みのブロックを後でレポートをファイル名と行番号が格納されます。 余分なパラメーターを指定することについて心配する必要はありません。マクロをするを行います。  
  
 使用しない場合でも`DEBUG_NEW`リーク検出の取得がデバッグ モードで、上記で説明したソース ファイルの行番号のレポート作成しなくてもします。  
  
> [!NOTE]
>  この演算子をオーバーライドする場合は上書きする必要ありますも**削除**です。 標準ライブラリを使用しないでください **_new_handler**関数。  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`で使用されるクラス、`CObject`例です。  
  
 [!code-cpp[NVC_MFCCObjectSample#16](../../mfc/codesnippet/cpp/cobject-class_9.h)]  
  
##  <a name="serialize"></a>  Cobject::serialize  
 アーカイブに対して、このオブジェクトの読み取りまたは書き込みを行います。  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
 `ar`  
 A`CArchive`またはからにシリアル化するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 オーバーライドする必要があります`Serialize`シリアル化しようとする各クラスにします。 オーバーライドされた`Serialize`呼び出す必要があります最初、`Serialize`基底クラスの関数。  
  
 使用することも必要があります、 [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial)クラスの宣言でマクロを使用する必要があります、 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)マクロで実装します。  
  
 使用して[場合](../../mfc/reference/carchive-class.md#isloading)または[用](../../mfc/reference/carchive-class.md#isstoring)をアーカイブの読み込みまたは保存するかどうかを判断します。  
  
 `Serialize` によって呼び出される[CArchive::ReadObject](../../mfc/reference/carchive-class.md#readobject)と[CArchive::WriteObject](../../mfc/reference/carchive-class.md#writeobject)です。 これらの関数が関連付けられている、`CArchive`挿入演算子 ( **< \<**) と抽出演算子 ( **>>**)。  
  
 シリアル化の例については、記事を参照してください。[シリアル化: オブジェクトのシリアル化](../../mfc/serialization-serializing-an-object.md)です。  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`すべてで使用されるクラス`CObject`例です。  
  
 [!code-cpp[NVC_MFCCObjectSample#13](../../mfc/codesnippet/cpp/cobject-class_10.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)



