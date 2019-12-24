# รายงานผลการทดลอง

<นางสาวอาทิตยา ฉิมมาแก้ว> <603410321-2>

## คำสั่งการแสดงผลผ่าน Logcat
import android.util.Log

Debug log --> แสดงข้อมูลข้อความสำหรับ Debug
Log.d("Tag", "msg");


Error log --> แสดงข้อมูลข้อความ Error ของโค้ด
Log.e("Tag", "msg");


Info log --> แสดงจ้อมูลข้อความที่ไม่จำเป็น
Log.i("Tag", "msg");


Verbose log --> แสดงข้อมูลข้อความที่ไม่จำเป็น
Log.v("tag", "msg");


Warning log --> แสดงข้อมูลข้อความการเตือนข้อผิดพลาดของโปรแกรม
Log.w("tag", "msg");

## SNACKBAR และ TOST

คำสั่งแสดง Snackbar
Snackbar.make(view, "Replace with your own action", Snackbar.LENGTH_LONG)


คำสั่งแสดง Tost
Toast.makeText(this, "Replace with your own action", Toast.LENGTH_SHORT).show()

## Android LiveCycle Activity

จงอธิบาการทำงานของเมธอทต่อไปนี้ ว่าเกิดขึ้นเมื่อใดของโปรแกรม พร้อมแสดงตัวอย่างโค้ดการทำงานของเมธอท (กำหนดให้แสดง log message เมื่อมีการทำงานของเมธอท)

1. onCreate() -> เป็น เMethod  ่ไว้ใช้เรียกเมื่อสร้างกิจกรรมใหม่ในการเข้าตัว Application
override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
        setSupportActionBar(toolbar)}

2. onStart() -> เป็น Method ที่ไว้ใช้เรียกเมื่อเรากลับเข้ามาใช้ Application นี้อีกครั้ง
override fun onStart() {
        super.onStart()
        Log.i("Ac Start", "onStart")
        }

3. onResume() -> เป็น Method ที่ไว้ทำงานกิจกรรมขณะที่ถูกใช้งานแล้ว
override fun onResume() {
        super.onResume()
        Log.i("onResume", "Ac resume")
        }

4. onPause() -> เป็น Method ที่ทำงานในขณะที่ Application ได้หยุดการทำงานแล่วแต่เรายังสามารถมองเห็นได้
override fun onPause() {
        super.onPause()
        Log.i("Ac Pause", "onPause")
        }

5. onStop() -> เป็น Method ที่แสดงสถานะของ Application นี้ได้หยุดทำงานแล้ว
override fun onStop() {
        super.onStop()
        Log.i("Ac Stop", "onStop")
        }

6. onDestroy() -> เป็น Method ที่จะทำงานเมื่อลบกิจกรรมออกแล้ว
override fun onDestroy() {
        super.onDestroy()
        Log.i("Ac Destroy", "onDestroy")
        }

7. onRestart() -> เป็น Method ที่เรียกให้ Application นี้กลับมาใช้งานได้อีกครั้ง
override fun onRestart() {
        super.onRestart()
        Log.i("Ac Restart", "onRestart")
        }

## Start new Activity

คำสั่งสำหรับเปิด activity ใหม่
var i = Intent(this,Main2Activity::class.java)
            startActivity(i)

คำสั่งสำหรับเปิด activity ใหม่ ผ่านเมนู setting
 override fun onOptionsItemSelected(item: MenuItem): Boolean {
        // Handle action bar item clicks here. The action bar will
        // automatically handle clicks on the Home/Up button, so long
        // as you specify a parent activity in AndroidManifest.xml.
        return when (item.itemId) {
            R.id.action_settings -> {
                var i = Intent(this,Main2Activity::class.java)
                startActivity(i)
                return true
            }
            R.id.action_settings -> true
            else -> super.onOptionsItemSelected(item)
        }
    }
