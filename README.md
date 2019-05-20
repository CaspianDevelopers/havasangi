# havasangi
payam
public class HavaSangi
    {
        public static string Grohe_1(string message_1, int nohe_message, int mokhtasat_tol, int mokhtasat_arz)//ورودی یک رشته متن و سه عدد مجزا وارد میشود//
        {

            string eroor_1="";
            string eroor_2="";
            string eroor_3="";

            if (message_1 == "METB")////METBپیام هواسنجی بالستیکی میباشد/////
            {
                eroor_3 = "پیام هواسنجی بالستیکی";
            }
            else
            {
                eroor_3 = "پیام نامشخص بالستیکی";
            }
////////////////////////////////////////////////////
            if (nohe_message == 2)
            {
                eroor_2 = "این پیام بر ای پدافند هوایی و ";
            }
            else
            {
                eroor_2 = "توپخانه";
            }
            /////////////////////////////////////////////////
         int mantaghe=0;
           
            
                if (mokhtasat_tol >= 0 && mokhtasat_tol <= 90 && mokhtasat_arz >= 0)
                {
                    mantaghe = 3;
                }
                if (mokhtasat_tol >= 90 && mokhtasat_tol <= 180 && mokhtasat_arz >= 0)
                {
                    mantaghe = 2;
                }
                if (mokhtasat_tol <= 0 && mokhtasat_tol >= -90 && mokhtasat_arz >= 0)
                {
                    mantaghe = 0;
                }
                if (mokhtasat_tol <= -90 && mokhtasat_tol >= -180 && mokhtasat_arz >= 0)
                {
                    mantaghe = 1;
                }

                if (mokhtasat_arz < 0 && mokhtasat_tol >= 0 && mokhtasat_tol <= 90)
                {
                    mantaghe = 8;
                }
                if (mokhtasat_arz < 0 && mokhtasat_tol > 90 && mokhtasat_tol > 180)
                {
                    mantaghe = 7;
                }
                if (mokhtasat_arz < 0 && mokhtasat_tol < 0 && mokhtasat_tol >= -90)
                {
                    mantaghe = 5;
                }
                if (mokhtasat_arz < 0 && mokhtasat_tol < -90 && mokhtasat_tol >= -180)
                {
                    mantaghe = 6;
                }

                ///////////////////////////////////////////////////////////////////////////////
           


            /////TEST OK///
            return eroor_3+" "+eroor_2+" "+"منطقه"+mantaghe.ToString()+"جهانی میباشد";
            //

        }

        ///TODO GROHE DOVOM///
        public static string Grohe_2_arz(int tol_arz)
        {
            string arz_ = "";
            int arz = 0;
            
            int arz_asli = 0;

            int counter = tol_arz.ToString().Length;

            if (counter == 6)
            {
                arz = int.Parse(tol_arz.ToString().Substring(0, 3));
               // tol= int.Parse(tol_arz.ToString().Substring(3,3));
            }

            if (int.Parse(arz.ToString().Substring(2, 1)) == 0)
            {
                arz_asli = int.Parse(arz.ToString().Substring(0, 2));
                arz_ = arz_asli.ToString();
            }
            else
            {
                arz_asli = int.Parse(arz.ToString().Substring(2, 1)) * 60;
                arz_asli = int.Parse(arz_asli.ToString().Substring(0, 2));
                arz_ = arz.ToString().Substring(0, 2) + "/" + arz_asli.ToString();
            }
            ////654123//
            //   ///

            return arz_;
        }
        /// <summary>
        /// test ok////
        /// </summary>
        /// <param name="tol_arz"></param>
        /// <returns></returns>
        public static string Grohe_2_tol(int tol_arz)
        {
            string tol_ = "";
            int tol = 0;

            int arz_asli = 0;

            int counter = tol_arz.ToString().Length;

            if (counter == 6)
            {
                tol = int.Parse(tol_arz.ToString().Substring(3, 3));
               
            }

            if (int.Parse(tol.ToString().Substring(2, 1)) == 0)
            {
                arz_asli = int.Parse(tol.ToString().Substring(0, 2));
                tol_ = arz_asli.ToString();
            }
            else
            {
                arz_asli = int.Parse(tol.ToString().Substring(2, 1)) * 60;
                arz_asli = int.Parse(arz_asli.ToString().Substring(0, 2));
                tol_ = tol.ToString().Substring(0, 2)+"درجه" + "/" + arz_asli.ToString()+"دقیقه";
            }
            ////654123//
            //   ///

            return tol_;
            ///test ok////
        }

        public static string Grohe_3(int date)
        {
            int modat_radioson = 0;
            string data_time = "";
            int daghige = 0;
            int saat = 0;
            string tarikh = "";
            string rozegari = "";
            string mahejari = "";
            int roz = 0;
            int counter = date.ToString().Length;
            if (counter == 6)
            {
                if (int.Parse(date.ToString().Substring(0, 2)) <= 24)
                {
                    roz = int.Parse(date.ToString().Substring(0, 2));
                    
                }

                tarikh = int.Parse(date.ToString().Substring(0, 2)).ToString();
                saat = int.Parse(date.ToString().Substring(2, 2));
                daghige= int.Parse(date.ToString().Substring(4, 1))*60;
                daghige = int.Parse(daghige.ToString().Substring(0, 2));
            }
            //////تاریخ روز جاری/////
            PersianCalendar pc=new PersianCalendar();
            ///211452///

            string myday = DateTime.Now.DayOfWeek.ToString();
            if (myday == DayOfWeek.Saturday.ToString())
                rozegari = "شنبه";
            else if (myday == DayOfWeek.Sunday.ToString())
                rozegari = "یکشنبه";
            else if (myday == DayOfWeek.Monday.ToString())
                rozegari = "دوشنبه";
            else if (myday == DayOfWeek.Tuesday.ToString())
                rozegari = "سه شنبه";
                
            else if (myday == DayOfWeek.Wednesday.ToString())
                rozegari = "چهارشنبه";
            else if (myday == DayOfWeek.Thursday.ToString())
                rozegari = "پنج شنبه";
            else if (myday == DayOfWeek.Friday.ToString())
                rozegari = "جمعه";
            ///////////////////////////////////////////////
            ///
            ////جهت گرفتن ماه جاری///////

            mahejari = pc.GetMonth(DateTime.Now).ToString();
            //////////////////////////////////
            
            /////////////////////////////////////
            modat_radioson = int.Parse(date.ToString().Substring(5, 1));
            ///
            data_time = "این پیام در مورخه"+" " + rozegari +""+ tarikh + "/ " + mahejari + " در ساعت" + daghige + " :" + saat +
                        " و به مدت اعتبار" + modat_radioson +" ساعت"+" "+ " از رادیوسن ارسال شده است";
            return data_time.ToString();

            //////////////Test ok////////////////////////////
        }

        public static double Grohe_4_ertfah(double data)
        {
            int ERTAFAH_radioson = 0;
           
         
           int conter = data.ToString().Length;//5
           if (conter == 5)
           {
               ERTAFAH_radioson = int.Parse(data.ToString().Substring(0, 2))*10;
            }
           else if(conter == 4)
           {
               ERTAFAH_radioson = int.Parse(data.ToString().Substring(0, 1)) * 10;
            }
           else if(conter == 6)
           {
               ERTAFAH_radioson = int.Parse(data.ToString().Substring(0, 3)) * 10;
            }
            
           ////037995//
           
            return ERTAFAH_radioson;
            ///////////////test ok/////////////////
        }

        public static double Grohe_4_feshar( double data)
        {
            int mohasebat = 0;
            double ertefahe_feshar = 0;

            int conter = data.ToString().Length;//5
            if (conter == 5)
            {
                ertefahe_feshar = int.Parse(data.ToString().Substring(2,3)) ;
                mohasebat = ertefahe_feshar.ToString().Length;
                if (mohasebat == 3)
                {
                    ertefahe_feshar = ertefahe_feshar / 10;
                }

                if (mohasebat == 2)
                {
                    ertefahe_feshar = ertefahe_feshar / 10 + 100;
                }
            }
            else if (conter == 4)
            {
                ertefahe_feshar = int.Parse(data.ToString().Substring(1, 3));
                mohasebat = ertefahe_feshar.ToString().Length;
                if (mohasebat == 3)
                {
                    ertefahe_feshar = ertefahe_feshar / 10;
                }

                if (mohasebat ==2)
                {
                    ertefahe_feshar = ertefahe_feshar / 10 + 100;
                }
            }
            else if(conter == 6)
            {
                ertefahe_feshar = int.Parse(data.ToString().Substring(3, 3));
                mohasebat = ertefahe_feshar.ToString().Length;
                if (mohasebat == 3)
                {
                    ertefahe_feshar = ertefahe_feshar / 10;
                }

                if (mohasebat == 2)
                {
                    ertefahe_feshar = ertefahe_feshar / 10 + 100;
                }

            }

            return ertefahe_feshar;

            /////Test ok/////////////
            ///
            ///
            /// 
        }

        public static int Matn_grohe_1_line(double data)///پیدا کردن لاین هواسنجی/////
        {
            int line = 0;

            if (data.ToString().Length == 5)
            {
                line = int.Parse(data.ToString().Substring(0, 1));
            }
            else
            {
                line = int.Parse(data.ToString().Substring(0, 2));
            }
            return line;///ما 15 تا لاین هواسنجی داریم////
            ////032924///
            /// Test ok///
        }

        public static int Matn_grohe_1_Grabad(int data)///جهت مشخص کردن گرا باد////
        {
            int Gra = 0;
            if (data.ToString().Length == 5)
            {
                Gra = int.Parse(data.ToString().Substring(1, 2))*100;
            }
            else
            {
                Gra = int.Parse(data.ToString().Substring(2, 2))*100;
            }

            return Gra;//////گرا به میلیم است////
            ///032924//
            ///
            /// Test ok////
        }

        public static int Matn_grohe_1_Speed(int data)////////برای سرعت باد///
        {
            int speed = 0;
            if (data.ToString().Length == 5)
            {
                speed = int.Parse(data.ToString().Substring(3, 2)) ;
            }
            else
            {
                speed = int.Parse(data.ToString().Substring(4, 2)) ;
            }

            return speed ;////سرعت باد به نات است/////
            ///032924//
            ///
            /// Test ok////
        }

        //public static int Matn_grohe_2_hararat(int data)
        //{
        //    int hararat = 0;
        //    if (data.ToString().Length == 4)
        //    {
        //        hararat=int.Parse()
        //    }
        //}
    }
