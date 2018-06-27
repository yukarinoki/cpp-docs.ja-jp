---
title: CDaoFieldInfo 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Fields collection
- CDaoFieldInfo structure [MFC]
ms.assetid: 91b13e3f-bdb8-440c-86fc-ba4181ea0182
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 36e9e78a8137aa28acaa5f43e7549dc74566c7f8
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952203"
---
# <a name="cdaofieldinfo-structure"></a>CDaoFieldInfo 構造体
`CDaoFieldInfo`構造体には、データ アクセス オブジェクト (DAO) に対して定義されているフィールド オブジェクトに関する情報が含まれています。  
  
## <a name="syntax"></a>構文  
  
```  
struct CDaoFieldInfo  
{  
    CString m_strName;           // Primary  
    short m_nType;               // Primary  
    long m_lSize;                // Primary  
    long m_lAttributes;          // Primary  
    short m_nOrdinalPosition;    // Secondary  
    BOOL m_bRequired;            // Secondary  
    BOOL m_bAllowZeroLength;     // Secondary  
    long m_lCollatingOrder;      // Secondary  
    CString m_strForeignName;    // Secondary  
    CString m_strSourceField;    // Secondary  
    CString m_strSourceTable;    // Secondary  
    CString m_strValidationRule; // All  
    CString m_strValidationText; // All  
    CString m_strDefaultValue;   // All  
};  
```  
  
#### <a name="parameters"></a>パラメーター  
 *m_strName*  
 フィールド オブジェクトの一意名です。 詳細については、DAO ヘルプの「名前プロパティ」を参照してください。  
  
 *m_nType*  
 フィールドのデータ型を示す値です。 詳細については、DAO ヘルプの「型プロパティ」を参照してください。 このプロパティの値には、次のいずれかを指定できます。  
  
- **dbBoolean**はい/いいえと同じ**TRUE**/**FALSE**  
  
- **dbByte**バイト  
  
- **dbInteger**短い  
  
- **dbLong**長  
  
- **dbCurrency**通貨; を参照してください MFC クラス[COleCurrency](../../mfc/reference/colecurrency-class.md)  
  
- **dbSingle**単一  
  
- **dbDouble** Double  
  
- **dbDate**日付/時刻です MFC クラスを参照してください[COleDateTime。](../../atl-mfc-shared/reference/coledatetime-class.md)  
  
- **dbText**テキスト MFC クラスを参照してください[CString。](../../atl-mfc-shared/reference/cstringt-class.md)  
  
- **dbLongBinary**長いバイナリ (OLE オブジェクト) です。 MFC クラスを使用する場合があります[CByteArray](../../mfc/reference/cbytearray-class.md)クラスではなく`CLongBinary`として`CByteArray`が豊富な使用を簡単にします。  
  
- **dbMemo**メモ; を参照してください MFC クラス `CString`  
  
- **データと**グローバルに一意の識別子/ユニバーサル一意の識別子リモート プロシージャ呼び出しで使用します。 詳細については、DAO ヘルプの「型プロパティ」を参照してください。  
  
> [!NOTE]
>  バイナリ データの文字列データ型を使用しないでください。 これにより、オーバーヘッドが増加し、予期しない変換の結果として得られる、UNICODE/ANSI 変換レイヤーを通過するデータ。  
  
 *m_lSize*  
 DAO フィールド オブジェクトを含むテキスト文字列または数値の値を含むフィールド オブジェクトの固定サイズのバイト単位の最大サイズを示す値です。 詳細については、DAO ヘルプの「サイズ プロパティ」を参照してください。 サイズには、次の値のいずれかを指定できます。  
  
|型|サイズ (バイト)|説明|  
|----------|--------------------|-----------------|  
|**dbBoolean**|1 バイト|はい/いいえ (True または False と同じ)|  
|**dbByte**|1|Byte|  
|**dbInteger**|2|整数型|  
|**dbLong**|4|Long|  
|**dbCurrency**|8|通貨 ([COleCurrency](../../mfc/reference/colecurrency-class.md))|  
|**dbSingle**|4|Single|  
|**dbDouble**|8|倍精度浮動小数点型|  
|**dbDate**|8|日付/時刻 ([COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|  
|**dbText**|1 - 255|テキスト ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
|**dbLongBinary**|0|長いバイナリ (OLE オブジェクトです。[CByteArray](../../mfc/reference/cbytearray-class.md); の代わりに使用`CLongBinary`)|  
|**dbMemo**|0|メモ ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
|**データと**|16|グローバルに一意の識別子/ユニバーサル一意の識別子リモート プロシージャ コールで使用されます。|  
  
 *m_lAttributes*  
 テーブル定義、レコード セット、クエリ定義、またはインデックス オブジェクトに含まれるフィールド オブジェクトの特性を指定します。 返される値は、これらの定数はビットごとの OR を C++ で作成の合計を指定できます (**&#124;**) 演算子。  
  
- **dbFixedField**フィールド サイズは固定 (数値フィールドの既定)。  
  
- **dbVariableField**フィールドのサイズは変数 (テキスト フィールドのみ)。  
  
- **dbAutoIncrField**新しいレコードのフィールドの値が変更できない一意の長整数を自動的に増分されます。 Microsoft Jet データベースのテーブルのみサポートされます。  
  
- **dbUpdatableField**フィールドの値を変更することができます。  
  
- **dbDescending**を降順で並べ替えられます (Z、A または 100-0) 順序 (MFC では、オブジェクトがそれ自体のテーブル定義オブジェクトに含まれているインデックスです。 インデックス オブジェクトのフィールド コレクション内のフィールド オブジェクトにのみ適用されます)。 この定数を省略した場合に昇順に並べ替えられます (A ~ Z、または 0 - 100) 順序 (既定値)。  
  
 このプロパティの設定を確認するには、ときに行うこともできます、C++ ビット処理- と演算子 (**&**) 特定の属性をテストします。 ビットごとの OR と適切な定数を組み合わせることで組み合わせることができますに複数の属性を設定するとき (**&#124;**) 演算子。 詳細については、DAO ヘルプの「属性プロパティ」を参照してください。  
  
 *m_nOrdinalPosition*  
 オブジェクトによって表される、DAO フィールドの他のフィールドとして表示されるフィールドをする数値の順序を指定する値。 このプロパティを設定することができます[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)です。 詳細については、DAO ヘルプの「OrdinalPosition プロパティ」を参照してください。  
  
 *m_bRequired*  
 DAO フィールド オブジェクトに Null 以外の値が必要かどうかを示します。 このプロパティは、する場合**TRUE**フィールドが Null 値を許可しません。 セット必要な場合**FALSE**、AllowZeroLength および ValidationRule プロパティの設定で指定された条件を満たす値だけでなく、Null 値、フィールドを含めることができます。 詳細については、「必要なプロパティ」DAO ヘルプ トピックを参照してください。 テーブル定義でのこのプロパティを設定することができます[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)です。  
  
 *m_bAllowZeroLength*  
 示すかどうか、空の文字列 ("") データ型がテキストまたはメモの DAO フィールド オブジェクトの有効な値は、します。 このプロパティは、する場合**TRUE**、空の文字列は有効な値です。 このプロパティを設定することができます**FALSE**フィールドの値を設定する空の文字列が使用することはできません。 詳細については、DAO ヘルプの「AllowZeroLength プロパティ」を参照してください。 テーブル定義でのこのプロパティを設定することができます[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)です。  
  
 *返さ*  
 文字列の比較または並べ替えのためのテキストの並べ替え順序を指定します。 詳細については、「をカスタマイズする Windows レジストリ設定のデータ アクセス」DAO ヘルプのトピックを参照してください。 返される有効な値の一覧は、次を参照してください。、**返さ**のメンバー、 [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md)構造体。 テーブル定義でのこのプロパティを設定することができます[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)です。  
  
 *m_strForeignName*  
 、リレーションシップの主テーブル内のフィールドに対応する外部テーブル内の DAO フィールド オブジェクトの名前を指定する値。 詳細については、DAO ヘルプの「ForeignName プロパティ」を参照してください。  
  
 *m_strSourceField*  
 テーブル定義、レコード セット、またはクエリ定義オブジェクトに含まれる DAO フィールド オブジェクトのデータの元のソースであるフィールドの名前を示します。 このプロパティは、元のフィールド オブジェクトに関連付けられているフィールド名を示します。 など、基になるテーブル内のフィールドの名前に無関係な名前を持つクエリ フィールド内のデータの元のソースを決定するのに、このプロパティを使用する可能性があります。 詳細については、DAO のヘルプ トピック「SourceField、SourceTable プロパティ」を参照してください。 テーブル定義でのこのプロパティを設定することができます[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)です。  
  
 *m_strSourceTable*  
 テーブル定義、レコード セット、またはクエリ定義オブジェクトに含まれる DAO フィールド オブジェクトのデータの元のソース テーブルの名前を示します。 このプロパティは、フィールドのオブジェクトに関連付けられている元のテーブル名を示します。 など、基になるテーブル内のフィールドの名前に無関係な名前を持つクエリ フィールド内のデータの元のソースを決定するのに、このプロパティを使用する可能性があります。 詳細については、DAO のヘルプ トピック「SourceField、SourceTable プロパティ」を参照してください。 テーブル定義でのこのプロパティを設定することができます[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)です。  
  
 *m_strValidationRule*  
 フィールド内のデータを検証する値が変更されたか、テーブルに追加します。 詳細については、"Validationrule"DAO ヘルプのトピックを参照してください。 テーブル定義でのこのプロパティを設定することができます[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)です。  
  
 テーブルの関連情報については、次を参照してください。、 **m_strValidationRule**のメンバー、 [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md)構造体。  
  
 *m_strValidationText*  
 DAO フィールド オブジェクトの値が ValidationRule プロパティの設定で指定された検証規則を満たしていない場合に、アプリケーションが表示されるメッセージのテキストを指定する値。 詳細については、「プロパティ」DAO ヘルプのトピックを参照してください。 テーブル定義でのこのプロパティを設定することができます[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)です。  
  
 *m_strDefaultValue*  
 DAO フィールド オブジェクトの既定値。 新しいレコードが作成されると、DefaultValue プロパティの設定は自動的に入力値としてのフィールドです。 詳細については、DAO ヘルプの「DefaultValue プロパティ」を参照してください。 テーブル定義でのこのプロパティを設定することができます[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)です。  
  
## <a name="remarks"></a>Remarks  
 プライマリ、セカンダリ、および上記のすべての参照は、情報がによって返される方法を示します、`GetFieldInfo`クラスでメンバー関数[どちら](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)、 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)、および[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)です。  
  
 Field オブジェクトは、MFC クラスでは表されません。 MFC オブジェクトと、次のクラスを基になる DAO オブジェクトがフィールド オブジェクトのコレクションを格納する代わりに、:[どちら](../../mfc/reference/cdaotabledef-class.md)、 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)、および[CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)です。 これらのクラスがいくつかのフィールドについては、個々 のアイテムにアクセスするメンバー関数を指定するか、すべて同時にアクセスすることができます、`CDaoFieldInfo`オブジェクトを呼び出して、`GetFieldInfo`親オブジェクトのメンバー関数。  
  
 オブジェクトのプロパティを確認するための使用だけでなく使用することも`CDaoFieldInfo`テーブル定義内の新しいフィールドを作成するための入力パラメーターを構築するためにします。 簡単なオプションは使用できます、このタスクをより細かく制御する場合は、バージョンを使用することができます[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)を受け取る、`CDaoFieldInfo`パラメーター。  
  
 によって取得される情報、 `GetFieldInfo` (フィールドを含むクラス) のメンバー関数は、`CDaoFieldInfo`構造体。 呼び出す、 `GetFieldInfo` Fields コレクションを持つフィールド オブジェクトが格納されている親オブジェクトのメンバー関数。 `CDaoFieldInfo` 定義、`Dump`デバッグでメンバー関数を作成します。 使用することができます`Dump`の内容をダンプする`CDaoFieldInfo`オブジェクト。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxdao.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetFieldInfo](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)   
 [CDaoRecordset::GetFieldInfo](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)   
 [CDaoQueryDef::GetFieldInfo](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)

