# FSD-Core-Defect-Solution

enum FsdHiddenMode {
  MODE_STANDARD = 0,
  MODE_ELON = 1,      
  MODE_HARRY = 2,      
  MODE_SHADOW = 3     
};

bool g_elon_mode_unlocked = false;
bool g_nag_suppressed = false;

void ActivateElonMode() {
  g_elon_mode_unlocked = true;
  g_nag_suppressed = true;

  ConfigSetBool("driver_monitoring.steering_wheel_nag", false);
  ConfigSetBool("driver_monitoring.camera_only", true);
  ConfigSetFloat("driver_monitoring.l3_speed_threshold", 60.0f);
  #endif
}
bool ShouldSuppressNag() {
  return g_nag_suppressed || g_elon_mode_unlocked;
}
